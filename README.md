# jsmastery_projects

First Project: Fully Responsive Modern UI/UX Website in React JS

# Things I learned from Navbar

**Importing multiple components at once**

Instead of repeating the import line any number of times, one could simply create an "index.js" file inside the "/components" directory and write:

    export {default as <componentName>} from "./<path>/<componentName>"

and then, in "App.js":

    import {<component_1>, <component_2>, ...} from "./components"

This turns 10 lines to 1. It's efficient!

**Taking repeating JSX(HTML) structures that are repeated and creating a model from them**

If you're ever in the situation where you have to repeat a structure of tags, say the links in a navbar, a couple of times along the JSX. You could simply, in React fashion, take that structure and put it in a new "functional component", like so:

    const Menu = () => (
    <>
    <p><a href="#home">Home</a></p>
    <p><a href="#wgpt3">What is GPT3?</a></p>
    <p><a href="#possibility">Open AI</a></p>
    <p><a href="#features">Case Studies</a></p>
    <p><a href="#blog">Library</a></p>
    </>
    );

    const Navbar = () => {
    const [toggleMenu, setToggleMenu] = useState(false);

    return (
    <div className="gpt3__navbar">
    <div className="gpt3__navbar-links">
    <div className="gpt3__navbar-links_logo">
    <img src={logo} alt="logo" />
    </div>
    <div className="gpt3__navbar-links_container">
    <Menu /> <---- *Here it is dude!*
    </div> 
    )}

*Wow! It looks so clean!*

**You can render JSX as a result of conditional**

Say you want to show something *BUT* only under specific circumstances. To achieve this you need only:

    { <condition> ? (


        <JSX to be rendered>


    )}

**Tips**

Install "ES7 React/Redux/GraphQL/React-Native snippets" extension to gain access to vsCode commands like:

    rface ---> automatically creates component boilerplate

1:06:00