# Basic Calculator

## Building the Calculator
Calculator has two main components:
1. Display:
2. Keys:
    -   Numbers (0-9)
    -   Operators (+, -, *, /)
    -   Decimal
    -   Equals
    -   Clear

### Listening to Key Pressed Events
Add a listener that will listen to the keys when pressed and will recognize the key type.

### Creating the Default Path
Consider what an average person would do when they use a calculator.
They can press any of the following keys:
1. A number key (0-9)
2. An operator key (+, -, *, /)
3. The decimal key
4. The equal key
5. The clear key

#### When a User Presses a Number Key
1. If 0 (the default number) is shown, replace it with the target number.
2. If non-zero number is shown, append the target number to it.

#### When a User Presses a Decimal Key
1. If decimal is pressed, it should display.
2. If a number is pressed after a decimal key, it should be appended on the display as well.

#### When a User Presses an Operator Key
1. If operator key is pressed, highlight the button so the user will know which operation will be executed.

#### When a User Presses a Number Key After an Operator Key
1. Release the operator key from its pressed state.
2. Replace previous number with new number.

#### When a User Presses the Equals Key
1. Calculate result of:
    - The **first number** entered
    - The **operator**
    - The **second number** entered
2. Replace displayed value with the result.

#### When a User Presses the Clear Key
1. All Clear (denoted `AC`) clears everything and resets the calculator to its initial state.
2. Clear Entry (denoted `CE`) clears the current entry. It keeps previous numbers in memory.

### Edge Cases

#### When a User Presses the Decimal Key
1. If the decimal is already displayed, then nothing should happen if the decimal key is pressed.
2. If the decimal key is pressed after an operator key, then the display should show `0.`.

#### When a User Presses an Operator Key
1. If an operator key is pressed, it should light up
2. Nothing should happen if the same operator key is pressed multiple times.
3. If another operator key is pressed after the first one, the first should be released and second one pressed.
4. If a number key is pressed, followed by an operator, a number, and another operator, the display should be updated with the new calculated value.

#### When a User Presses the Equals Key
1. Nothing should happen if the equals key is pressed before any operator has been pressed.
2. If a number has been pressed, followed by an operator, and then the equals key, the calculator should repeat the operation on the number itself.
3. If the equals key is pressed after a calculation, another calculation should be able to be performed subsequently (chaining multiple operations).
4. If a decimal or number key is pressed after the equals key, the display should be replaced with `0.` or the number respectively.
5. If an operator key is pressed right after the equals key, there should not be any calculations.

#### When a User Presses the Clear Key
1. If any key is pressed (except clear), `AC` should be changed to `CE`.
2. If `CE` is pressed, the display should read 0, and `CE` should be reverted to `AC` as its initial state.
3. If `AC` is pressed, reset the calculator to its initial state.