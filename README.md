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

We can also use CSSTansition from react-transition-group:

2. CSSTransition component takes some props:

   - in: boolean = render elements depending on the given value

   - timeout: number/object = for timing function
     it can take numeric value or an object
     ex { enter: 400, exit:100 }

   - classNames: object = adds classnames from local css file and adds those to the wraped elements.

     ex: classNames={{
         enter:"",
         enterActive: "ModalOpen",
         exit: "",
         exitActive:"ModalClosed"
     }}

We can also use TransitionGroup Component for rendering list elements:

1.  In case of TransitionGroup the "in" props is not required because it automaticly determines by the nature of the code to render dynamic components.
    +it will have a "component: String" prop which will be rendered. /ex : component="ul"/

2.  Every Dynamic components inside of the <TransitionGroup/> element must be wrapped by <Transition/> or <CSSTransition /> component.

    +classNames: it can also be configured as giving a trunk name:
    ex: <CSSTransition key={index} classNames="fade" timeout={300}></CSSTransition>
    =then in the global css will have classes named :
    .fade-enter {}
    .fade-enter-active {}
    .fade-exit {}
    .fade-exit-active{}
    for different state of the component.
