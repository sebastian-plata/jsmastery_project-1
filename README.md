# jsmastery_projects

First Project: Fully Responsive Modern UI/UX Website in React JS

# Things I learned from Navbar

**File strucutre**

Each component is stored in its own directory, named after themselves, and in turn every component directory is stored in a "/components" directory. 

*What is a component?*

A component is a segment of a webpage that can be iterated or used multiple times/ways across the page/site. Examples: navbars, articles and so on. Components can also be used to build "containers".

Very much like "components", containers are stored in their own directory named after themselves, and in turn every container directory is stored in a "/containers" directory. 

*What is a container?*

A container are bigger sections of the webpage that are build on components. Examples: header, footer, section and so on.

*Each component and article has its personal .css file*

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

Time-stamp: 1:06:00

# Things I learned from Header

**Import files using import**

JSX allows you to import assets and media you wish to include in your project by importing it in the component's file like:

    import <file> from '/<path>/<to>/<file.xxx>'

Which you can then use in JSX like your using a variable:

     <img src={<file>} alt="..." />

**Using flex:; do asign space in the layour more efficiently**

Normally Id assign porcentages through flex-basis property or width. However using flex property followed by a single number does the job much better.

    ...
    <div class="wrap">
    <div class="test-1">im test 1</div>
    <div class="test-2">im test 2</div>
    </div>

    .wrap {
        display: flex;
    }

    .test-1{
        flex: 1;
        /*
        flex-grow: 1;
        flex-shrink: 1;
        flex-basis: 0;
        */
    }
    test-2{
        flex: 1;
    }

    The code above assigns each of the divs with class="test-$" half the container. And they'll grow and shrink with the size of the ".wrap" container.

Now flex is a shorthand property for other three flexblox properties, namely: flex-grow, flex-shring, flex-basis.

    flex: <flex-grow> <flex-shrink> <flex-basis>;

*The property "flex-basis"* allows you to set the base width of an element inside a flexbox container (as long as the container is wider than the sum of widths of its children). If the container's width is lower than the sum of the widths of its children, the children will shrink.

*The property "flex-grow"* works kind of like the fr unit in CSS Grid. In the sense that it assigns a fraction of the container to the element. It also, determines how "fast" an element will grow compared to its siblings.
If pair siblings have the same value of "flex-grow" they will ocuppy the containers width evenly. Default value: 0.

*The property "flex-shrink"* It determines the rate at which an element will shrink compared to its siblings. If pair siblings have the same value of "flex-grow" they will ocuppy the containers width evenly. Default value: 1. 