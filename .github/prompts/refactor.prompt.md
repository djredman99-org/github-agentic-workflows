---
description: 'Refactor code to improve quality, readability, or performance. Use when: improving code structure, eliminating duplication, optimizing performance, modernizing code.'
---

# Code Refactoring Prompt

Refactor the selected code or specified file to improve its quality while maintaining functionality.

## Input Parameters

**Required**:
- Code to refactor (provide file path, selection, or paste code)

**Optional**:
- Specific goal (readability, performance, testability, modularity)
- Constraints (maintain API compatibility, no dependency changes)
- Target language version or framework version

## Refactoring Process

### 1. Analysis
Analyze the current code for:
- Code smells (duplication, long methods, complex conditionals)
- Performance bottlenecks
- Readability issues
- Testing gaps
- Design pattern opportunities

### 2. Planning
Before making changes, explain:
- What will be refactored and why
- Expected benefits
- Potential risks
- Whether tests need updating

### 3. Refactoring
Apply improvements such as:
- Extract Method: Break long functions into smaller ones
- Extract Variable: Name complex expressions
- Rename: Use clearer names
- Remove Duplication: DRY principle
- Simplify Conditionals: Reduce nesting, use guard clauses
- Introduce Design Patterns: Where appropriate

### 4. Verification
Ensure:
- ✅ Behavior is unchanged (run tests)
- ✅ Code is more readable
- ✅ Complexity is reduced
- ✅ Performance is maintained or improved
- ✅ Tests still pass

## Refactoring Types

### Extract Function
**Before**:
```python
def process_order(order):
    # Calculate total
    total = sum(item.price * item.quantity for item in order.items)
    tax = total * 0.08
    shipping = 10 if total < 50 else 0
    final_total = total + tax + shipping
    
    # Send confirmation
    email_body = f"Order total: ${final_total}"
    send_email(order.customer.email, "Order Confirmation", email_body)
```

**After**:
```python
def calculate_order_total(order):
    subtotal = sum(item.price * item.quantity for item in order.items)
    tax = subtotal * 0.08
    shipping = 10 if subtotal < 50 else 0
    return subtotal + tax + shipping

def send_order_confirmation(order, total):
    email_body = f"Order total: ${total}"
    send_email(order.customer.email, "Order Confirmation", email_body)

def process_order(order):
    total = calculate_order_total(order)
    send_order_confirmation(order, total)
```

### Simplify Conditionals
**Before**:
```python
def get_discount(customer):
    if customer.is_premium:
        if customer.orders_count > 10:
            return 0.20
        else:
            return 0.10
    else:
        if customer.orders_count > 5:
            return 0.05
        else:
            return 0
```

**After**:
```python
def get_discount(customer):
    if customer.is_premium and customer.orders_count > 10:
        return 0.20
    if customer.is_premium:
        return 0.10
    if customer.orders_count > 5:
        return 0.05
    return 0
```

### Replace Magic Numbers
**Before**:
```python
def is_adult(age):
    return age >= 18

def can_rent_car(age):
    return age >= 25
```

**After**:
```python
LEGAL_ADULT_AGE = 18
CAR_RENTAL_AGE = 25

def is_adult(age):
    return age >= LEGAL_ADULT_AGE

def can_rent_car(age):
    return age >= CAR_RENTAL_AGE
```

## Guidelines

- Make small, incremental changes
- Run tests after each change
- Commit working increments
- Don't change behavior and refactor simultaneously
- Focus on one improvement at a time

## Example Usage

```
/refactor src/services/user_service.py - focus on extracting smaller functions
```

or

```
Refactor the following code to improve readability:
[paste code]
```

## Success Criteria

Refactored code should be:
- ✅ Easier to understand
- ✅ Easier to test
- ✅ Easier to modify
- ✅ More maintainable
- ✅ Functionally equivalent
