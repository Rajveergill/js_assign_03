A closure is a function having access to the parent scope, even after the parent function has closed.
Closures are functions that refer to independent (free) variables (variables that are used locally, but defined in an enclosing scope).
In other words, these functions 'remember' the environment in which they were created.
var add = (function () {
    var counter = 0;
    return function () {return counter += 1;}
})();

add();
add();
add();
The variable add is assigned the return value of a self-invoking function.

The self-invoking function only runs once. It sets the counter to zero (0), and returns a function expression.

This way add becomes a function. The "wonderful" part is that it can access the counter in the parent scope.

This is called a JavaScript closure. It makes it possible for a function to have "private" variables.

The counter is protected by the scope of the anonymous function, and can only be changed using the add function.
JavaScript does not provide a native way of doing this, but it is possible to emulate private methods using closures. 
Private methods aren't just useful for restricting access to code:
they also provide a powerful way of managing your global namespace, keeping non-essential methods from cluttering up the public interface to your code.

