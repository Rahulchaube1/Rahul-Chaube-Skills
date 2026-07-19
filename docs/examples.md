# Real-World Examples

This document demonstrates the core principles of **Rahul-Chaube-Skills (RCS)** using concrete code examples. Each section presents a common LLM mistake and shows the correct, RCS-aligned approach.

---

## 🧠 1. Think Before Coding

### Example 1: Hidden Assumptions

**User Request**: "Add a feature to export transaction logs."

#### ❌ What Agents Do (Wrong Assumptions)

The agent silently assumes details and writes bloated code:

```python
def export_transactions():
    # Silently assumes database format, CSV columns, and file storage path
    logs = Transaction.query.all()
    with open('/tmp/transactions.csv', 'w') as f:
        writer = csv.writer(f)
        for log in logs:
            writer.writerow([log.id, log.amount, log.timestamp])
    return "Exported!"
```

#### ✅ RCS Alignment (Surface Assumptions First)

The agent stops and requests clarification before editing:

```
Before implementing, I have identified several assumptions that require clarification:
1. **Scope**: Should we export all transactions, or should we filter by date/user?
2. **Format**: You requested an "export". Did you mean:
   - A downloadable CSV file via a REST API endpoint?
   - A background task that uploads a JSON file to AWS S3 and emails the link?
3. **Fields**: Which transaction columns are required? (e.g. ID, Amount, Timestamp, Status, UserID).
4. **Volume**: If logs exceed 100k rows, we should implement streaming. What is the expected scale?

Simplest approach: Create an endpoint that returns paginated JSON logs.
Please clarify your requirements.
```

---

## 💡 2. Simplicity First

### Example 1: Premature Abstractions

**User Request**: "Write a function to hash passwords."

#### ❌ What Agents Do (Overengineered)

```python
from abc import ABC, abstractmethod

class PasswordHasher(ABC):
    @abstractmethod
    def hash(self, password: str) -> str: pass

class BcryptHasher(PasswordHasher):
    def hash(self, password: str) -> str:
        return bcrypt.hashpw(password.encode(), bcrypt.gensalt()).decode()

class HasherFactory:
    @staticmethod
    def get_hasher(algorithm: str) -> PasswordHasher:
        if algorithm == "bcrypt": return BcryptHasher()
        raise ValueError("Unsupported algorithm")
```

#### ✅ RCS Alignment (Keep It Simple)

```python
import bcrypt

def hash_password(password: str) -> str:
    """Hash password using bcrypt."""
    return bcrypt.hashpw(password.encode(), bcrypt.gensalt()).decode()
```

---

## ✂️ 3. Surgical Changes

### Example 1: Collateral Formatting Changes

**User Request**: "Fix the typo in the error response message."

#### ❌ What Agents Do (Reformatting Adjacent Code)

```diff
  def process_payment(amount):
-     if amount <= 0:
-         raise ValueError('amount must be positive')
-     # Charge customer card
-     charge = stripe.Charge.create(amount=amount)
-     return charge
+     """Process Stripe payments."""
+     if amount <= 0:
+         raise ValueError("Amount must be greater than zero.")
+
+     # Charge card
+     charge = stripe.Charge.create(
+         amount=amount,
+         currency="usd"
+     )
+     return charge
```

#### ✅ RCS Alignment (Surgical Edit)

```diff
  def process_payment(amount):
      if amount <= 0:
-         raise ValueError('amount must be positive')
+         raise ValueError('Amount must be positive')
      # Charge customer card
      charge = stripe.Charge.create(amount=amount)
      return charge
```
