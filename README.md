# sc-moonlight.github.io

I do most of my coding now for a corporation.  There enough interesting problems there that I don't do much on the side.

This site will be for the small things I build outside of work that others might find useful

# Java

Java added [Functional interfaces](https://docs.oracle.com/javase/8/docs/api/java/util/function/Function.html) in JDK 8, but there are times I really wish there was a similar reference for properties in classes.

Without it, we are often left to using string names for properties that still must match the property, but there is no link between the string and the property.

A common example is using Spring [Errors](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/validation/Errors.html) when validating a submitted form.

```java
errors.rejectValue("userId", "invalid");
```
In this case, "userId" should match the property in the object I'm validating.  If it doesn't? No error, and no way to know there is a problem until you stumble into it later.

So, I built out a simple annotation processor [meta-fields](https://github.com/sc-moonlight/meta-fields), that will create a Meta class for you to reference those properties.