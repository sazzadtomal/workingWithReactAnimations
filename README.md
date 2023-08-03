Normal CSS Limitations:

=> cannot use css closing animation because conditional elements instantly removed from the dom.

Use React-transition-group to tackle this problem:

1. Transition component from React-transition-group wraps an element.

   +It provides 4 states:
   +Entering,
   +Entered,
   +exting,
   +exited

   This states are provided to the wrapped element as a function arguments

2. Transition component takes some props:

   - in: boolean = render elements depending on the given value

   - timeout: number/object = for timing function
     it can take numeric value or an object
     ex { enter: 400, exit:100 }

   It helps to complete the animation before removing the componenent.

   - mountOnEnter: boolean = render the component depending on the "in" prop

   - unmountOnExit: boolean = removes the component depending on the "in" prop

   It also can take some callback functions as props:
   ex :+OnEnter (also for other states also)
