### Step-by-Step Guide

#### Step 1: 🚀 Initial Setup

- Clone the repository: `git clone https://github.com/Aaqib925/decision-tree-node.git`
- Navigate: `cd express-typescript-2024`
- Install dependencies: `npm ci`

#### Step 2: ⚙️ Environment Configuration

- Create `.env`: Copy `.env.template` to `.env`
- Update `.env`: Fill in necessary environment variables

#### Step 3: 🏃‍♂️ Running the Project

- Development Mode: `npm run dev`
- Building: `npm run build`
- Production Mode: Set `.env` to `NODE_ENV="production"` then `npm run build && npm run start`

To include the example payloads in your `README.md` on GitHub, you can structure them in a clear and concise manner to ensure they are easy to read and understand. Below is a suggested format:

---

## Example Payloads for `/execute-tree` Endpoint

This section provides example payloads demonstrating the structure expected for different scenarios when using the `/execute-tree` API. 

### 1. Simple SMS Action

This example sends an SMS to a specified phone number.

```json
{
  "type": "SendSMS",
  "phoneNumber": "+1234567890"
}
```

### 2. Simple Email Action

This example sends an email from the specified sender to the receiver.

```json
{
  "type": "SendEmail",
  "sender": "noreply@example.com",
  "receiver": "user@example.com"
}
```

### 3. Condition Node

This example demonstrates a conditional action based on a JavaScript expression. If the condition evaluates to `true`, it sends an SMS. Otherwise, it sends an email.

```json
{
  "type": "Condition",
  "expression": "new Date().getFullYear() === 2024",
  "trueAction": {
    "type": "SendSMS",
    "phoneNumber": "+1234567890"
  },
  "falseAction": {
    "type": "SendEmail",
    "sender": "noreply@example.com",
    "receiver": "user@example.com"
  }
}
```

### 4. Loop Node

This example demonstrates a loop node that executes a subtree 3 times. The subtree checks a condition and sends an SMS if the condition is `true`.

```json
{
  "type": "Loop",
  "iterations": 3,
  "subtree": {
    "type": "Condition",
    "expression": "new Date().getDate() === 1",
    "trueAction": {
      "type": "SendSMS",
      "phoneNumber": "+1234567890"
    }
  }
}
```

### 5. Complex Decision Tree

This payload shows a more complex decision tree combining conditions, loops, and actions.

```json
{
  "type": "Condition",
  "expression": "new Date().getMonth() === 11",
  "trueAction": {
    "type": "Loop",
    "iterations": 5,
    "subtree": {
      "type": "SendEmail",
      "sender": "holiday@example.com",
      "receiver": "user@example.com"
    }
  },
  "falseAction": {
    "type": "SendSMS",
    "phoneNumber": "+1234567890"
  }
}
```
