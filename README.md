def bisection_method(function, a, b, abs_error):
    error_accept = abs_error  # Added missing variable for error acceptance

    def f(x):
        return eval(function.replace('x', str(x)))  # Define the function using eval

    error = abs(b - a)
    while error > error_accept:
        c = (b + a) / 2
        if f(a) * f(b) >= 0:
            print("No root")
            quit()
        elif f(c) * f(a) < 0:
            b = c
            error = abs(b - a)
        elif f(c) * f(b) < 0:
            a = c
            error = abs(b - a)
        else:
            print("No root")
            quit()

    print(f"The error is {error}")
    print(f"The lower boundary, a, is {a} and the upper boundary, b, is {b}")

# Example usage:
bisection_method("x**2 - 3*x + 1", 0, 2, 0.01)
