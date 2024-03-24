# Read-Only & Write Only Properities

---

## Read-Only

---

**Immutable Data:**

Read-Only properties are commonly used when you want to create an object with data that does not change after the object is created. 

For example, in a class representing a BirthDay, you could have a read-only property for the Date.

Once the BirthDate object is created, the Date should not change.

**Computed Data:**

Read-only properties are also used when the property value is computed from other data.

For example, in a Rectangle class, you could have a read-only property for the Area that computes the area of the rectangle from its Width and Height.

## Write-only

---

**Sensitive Data:**

Write-only properties can be used for sensitive data that should be set, but not read from the application.

For example, in a UserCredentials class, you might have a write-only property for the Password,

The application needs to set the password, but it should not be able to get the password once it’s set.

**Triggering Actions:**

A write-only property can also be used to trigger some action when data is set.

For example, in a a Logger class, you could have a write-only property Message that writes a message to a log file when set.