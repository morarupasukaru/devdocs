# Web APIs

Here is a list of useful [Web APIs](https://developer.mozilla.org/en-US/docs/Web/API) to develop standard web applications.

* [**DOM - Document Object Model**](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model): 
  to manipulate elements of HTML
  * [Window Object](#Window-Object) properties are globally available in browser like 
    [document](https://developer.mozilla.org/en-US/docs/Web/API/Document)
  * [DOM Manipulations](#DOM-Manipulations) are mainly available with global object 
    [document](https://developer.mozilla.org/en-US/docs/Web/API/Document) or
    [Element](https://developer.mozilla.org/en-US/docs/Web/API/Element) /
    [Node](https://developer.mozilla.org/en-US/docs/Web/API/Node) objects
  * [Events](#Events) can be triggered by user actions or programmatically and can be listen 
    by [event-handlers](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Events#dom_event_handler_list)
* [**Web Storage API**](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API): 
  to store data locally within user's browser; 
  see [guide](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API/Using_the_Web_Storage_API)
  * [window.localStorage](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage), 
    [window.sessionStorage](https://developer.mozilla.org/en-US/docs/Web/API/Window/sessionStorage) 
    returns a [Storage](https://developer.mozilla.org/en-US/docs/Web/API/Storage) 
    object to store data as String
  * API: [SessionStorage.setItem()](https://developer.mozilla.org/en-US/docs/Web/API/Storage/setItem) / 
    [getItem()](https://developer.mozilla.org/en-US/docs/Web/API/Storage/getItem) / 
    [removeItem()](https://developer.mozilla.org/en-US/docs/Web/API/Storage/removeItem) / 
    [clear()](https://developer.mozilla.org/en-US/docs/Web/API/Storage/clear)
  * [JSON.parse()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/parse) / 
    [stringify()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify) 
    must be used to store/retrieve object or array from Storage
* [**Fetch API**](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API): 
  to perform server requests (and replace 
  [XMLHttpRequest](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest));
  see [guide](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch)
* [Console API](https://developer.mozilla.org/en-US/docs/Web/API/Console_API) 
  to ease debugging by using the methods of the [Console](https://developer.mozilla.org/en-US/docs/Web/API/Console) 
  global object
* [URL API](https://developer.mozilla.org/en-US/docs/Web/API/URL_API): to compose and manipulate 
  [URL](https://developer.mozilla.org/en-US/docs/Web/API/URL)s; see also: 
  * [window.location](https://developer.mozilla.org/en-US/docs/Web/API/Window/location) 
      returns a [Location](https://developer.mozilla.org/en-US/docs/Web/API/Location) 
      to manipulate actual display URL
  * [JavaScript](./JavaScript.md) provide methods to encode/decode URI: 
      [encodeURIComponent()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/encodeURIComponent) / 
      [decodeURIComponent()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/decodeURIComponent)
* [Fullscreen API](https://developer.mozilla.org/en-US/docs/Web/API/Fullscreen_API): 
  to display a specific Element in full-screen mode; 
  see [guide](https://developer.mozilla.org/en-US/docs/Web/API/Fullscreen_API/Guide)
* [Presentation](https://developer.mozilla.org/en-US/docs/Web/API/Presentation_API): to support dual-screen
* [Page Visibility](https://developer.mozilla.org/en-US/docs/Web/API/Page_Visibility_API): 
  to know when a document becomes visible or hidden
  (see also [stackoverflow question](https://stackoverflow.com/questions/1060008/is-there-a-way-to-detect-if-a-browser-window-is-not-currently-active/9502074#9502074)
  and [ifvisible.js](https://github.com/serkanyersen/ifvisible.js) JS lib)
* [Intersection Observer API](https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API): 
  to support e.g. infinite-scrolling; 
  see [scroll-aware navigation bar](https://academind.com/learn/javascript/scroll-aware-navigation/)
* [Constraint validation API](https://developer.mozilla.org/en-US/docs/Web/API/Constraint_validation) 
  to apply custom validation on user inputs; 
  see [guide](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation#Validating_forms_using_JavaScript)
* [Web Workers](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API): 
  to run a script operation in a background thread; 
  see [guide](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Using_web_workers)
* [Service Worker API](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API): 
  to provide proxy servers between web apps, the browser, and the network; 
  see [guide](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API/Using_Service_Workers)
* [Broadcast Channel API](https://developer.mozilla.org/en-US/docs/Web/API/Broadcast_Channel_API): 
  to communicate between browsing contexts of same [origin](https://developer.mozilla.org/en-US/docs/Glossary/origin)
* [Channel Messaging API](https://developer.mozilla.org/en-US/docs/Web/API/Channel_Messaging_API): 
  to communicate between browsing contexts of different origins; 
  see [guide](https://developer.mozilla.org/en-US/docs/Web/API/Channel_Messaging_API/Using_channel_messaging)
* [Notification API](https://developer.mozilla.org/en-US/docs/Web/API/Notifications_API): 
  allow web workers to notifications to end user; 
  see [guide](https://developer.mozilla.org/en-US/docs/Web/API/Notifications_API/Using_the_Notifications_API)
* [Server-sent Events (SSE)](https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events): 
  enable push communication from server to client (one way communication) with an always open HTTP connection, 
  see [guide](https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events/Using_server-sent_events)
  * limitation: browser forbid more than 2-6 connections per domain name
  * server does not receive information of loss client (server will still emits)
* [Websockets API](https://developer.mozilla.org/en-US/docs/Web/API/Websockets_API): 
  enable bidirectional communication between client and server with full-duplex TCP connection 
  (HTTP still used for authentication); 
  see [client](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API/Writing_WebSocket_client_applications)
  and [server](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API/Writing_WebSocket_servers) guides
  * more complex than Server-sent Events (could require infrastructure changes)
* [Push API](https://developer.mozilla.org/en-US/docs/Web/API/Push_API): allow web notifications in conjunction with 
  [Notification API](https://developer.mozilla.org/en-US/docs/Web/API/Notifications_API) and 
  [Service Work API](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API); 
  (use [web push protocol](https://tools.ietf.org/html/rfc8030) underneath normally)
  * is still *experimental* (at 01.10.2020)

*(Page mainly written in 2019, last update: september 2020)*

[*Go to parent page*](../README.md)


## DOM

The [Document Object Model](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model) (DOM) allow to 
manipulate elements of HTML documents.

### Window Object

main features of [Window](https://developer.mozilla.org/en-US/docs/Web/API/Window) Object 
* [window.location](https://developer.mozilla.org/en-US/docs/Web/API/Window/location) returns a 
  [Location](https://developer.mozilla.org/en-US/docs/Web/API/Location) object. You can also assign a String.
* [window.history](https://developer.mozilla.org/en-US/docs/Web/API/Window/history) returns a 
  [History](https://developer.mozilla.org/en-US/docs/Web/API/History) object which allow to navigate in session history 
  with [back/forward()](https://developer.mozilla.org/en-US/docs/Web/API/History#Methods)
* [window.navigator](https://developer.mozilla.org/en-US/docs/Web/API/Window/navigator) returns a 
  [Navigator](https://developer.mozilla.org/en-US/docs/Web/API/Navigator) object.
* [window.document](https://developer.mozilla.org/en-US/docs/Web/API/Window/document) returns a 
  [Document](https://developer.mozilla.org/en-US/docs/Web/API/Document) object and represents the web page loaded in 
  the browser. It's the root element of the 
  [DOM tree](https://developer.mozilla.org/en-US/docs/Web/API/Document_object_model/Using_the_W3C_DOM_Level_1_Core#what_is_a_dom_tree)
* [window.localStorage/sessionStorage allow to store data](#Web-Storage-API)
* [window.setTimeout()](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setTimeout) 
  sets a timer which executes a function once the timer expires
  * see also [Why Promises Are Faster Than setTimeout()?](https://dmitripavlutin.com/javascript-promises-settimeout/)
  * see also [Microtasks ](https://developer.mozilla.org/en-US/docs/Web/API/HTML_DOM_API/Microtask_guide)
* [window.postMessage()](https://developer.mozilla.org/en-US/docs/Web/API/Window/postMessage) and 
  [message](https://developer.mozilla.org/en-US/docs/Web/API/Window/message_event) event are used for cross-origin 
  communication, see [Channel Messaging API](https://developer.mozilla.org/en-US/docs/Web/API/Channel_Messaging_API)

[*Go to top*](#Web-APIs)


### DOM Manipulations

* single element selectors: [document.getElementById()](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById) /
  [querySelector()](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector), 
  [Element.querySelector()](https://developer.mozilla.org/en-US/docs/Web/API/Element/querySelector)
* multiple elements selectors:
  [document.getElementsByClassName()](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByClassName) / 
  [getElementsByTagName()](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByTagName) /
  [querySelectorAll](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelectorAll), 
  [Element.getElementsByClassName()](https://developer.mozilla.org/en-US/docs/Web/API/Element/getElementsByClassName) /
  [getElementsByTagName()](https://developer.mozilla.org/en-US/docs/Web/API/Element/getElementsByTagName) /
  [querySelectorAll](https://developer.mozilla.org/en-US/docs/Web/API/ParentNode/querySelectorAll)
* traversing the DOM: element.[children](https://developer.mozilla.org/en-US/docs/Web/API/ParentNode/children) /
  [firstElementChild](https://developer.mozilla.org/en-US/docs/Web/API/ParentNode/firstElementChild) /
  [lastElementChild](https://developer.mozilla.org/en-US/docs/Web/API/ParentNode/lastElementChild) /
  [parentElement](https://developer.mozilla.org/en-US/docs/Web/API/Node/parentElement) /
  [nextElementSibling](https://developer.mozilla.org/en-US/docs/Web/API/NonDocumentTypeChildNode/nextElementSibling) /
  [previousElementSibling](https://developer.mozilla.org/en-US/docs/Web/API/NonDocumentTypeChildNode/previousElementSibling)
* creating element: [document.createElement()](https://developer.mozilla.org/fr/docs/Web/API/Document/createElement) / 
  [createTextNode()](https://developer.mozilla.org/fr/docs/Web/API/Document/createTextNode), 
  [Node.appendChild()](https://developer.mozilla.org/en-US/docs/Web/API/Node/appendChild) / 
  [insertBefore()](https://developer.mozilla.org/en-US/docs/Web/API/Node/insertBefore)
* replace element: [Node.replaceChild(newElement, oldElement)](https://developer.mozilla.org/en-US/docs/Web/API/Node/replaceChild)
* remove element: [Node.removeChild](https://developer.mozilla.org/en-US/docs/Web/API/Node/removeChild)
* get/change class: [Element.className](https://developer.mozilla.org/en-US/docs/Web/API/Element/className) / 
  [classList](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList)
* get/change attribute: [Element.getAttribute()](https://developer.mozilla.org/en-US/docs/Web/API/Element/getAttribute) / 
  [setAttribute()](https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttribute) / 
  [hasAttribute()](https://developer.mozilla.org/en-US/docs/Web/API/Element/hasAttribute)
* get/change text content with [Element.textContent](https://developer.mozilla.org/en-US/docs/Web/API/Node/textContent) / 
  [innerText](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/innerText) 
  [(see differences)](https://developer.mozilla.org/en-US/docs/Web/API/Node/textContent#Differences_from_innerText) 
* get/change html content with [Element.innerHTML](https://developer.mozilla.org/en-US/docs/Web/API/Element/innerHTML)
* get/set id: [Element.id](https://developer.mozilla.org/en-US/docs/Web/API/Element/id)
* hints: convert ["live" NodeList](https://developer.mozilla.org/en-US/docs/Web/API/NodeList#Live_vs._Static_NodeLists) 
  or [HTMLCollection](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCollection) to Array with 
  [Array.from()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/from) 
  to reduce performance bottlenecks

[*Go to top*](#Web-APIs)


### Events

* [EventTarget.addEventListener('evt', function)](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener) / 
  [removeEventListener()](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/removeEventListener)
* [Events](https://developer.mozilla.org/en-US/docs/Web/Events):
  * mouse events:
    [click](https://developer.mozilla.org/en-US/docs/Web/API/Element/click_event), 
    [mousemove](https://developer.mozilla.org/en-US/docs/Web/API/Element/mousemove_event), 
    [dblclick](https://developer.mozilla.org/en-US/docs/Web/API/Element/dblclick_event), 
    [mousedown](https://developer.mozilla.org/en-US/docs/Web/API/Element/mousedown_event), 
    [mouseup](https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseup_event), 
    [mouseenter](https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseenter_event), 
    [mouseleave](https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseleave_event), 
    [mouseover](https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseover_event), 
    [mouseout](https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseout_event)
  * keyboard events: 
    [keydown](https://developer.mozilla.org/en-US/docs/Web/Events/keydown), 
    [keyup](https://developer.mozilla.org/en-US/docs/Web/Events/keyup)
  * form events: 
    [submit](https://developer.mozilla.org/en-US/docs/Web/Events/submit), 
    [invalid](https://developer.mozilla.org/en-US/docs/Web/Events/invalid)
  * focus events: 
    [focus](https://developer.mozilla.org/en-US/docs/Web/API/Element/focus_event), 
    [blur](https://developer.mozilla.org/en-US/docs/Web/API/Element/blur_event)
  * clipboard events: 
    [cut](https://developer.mozilla.org/en-US/docs/Web/API/Element/cut_event), 
    [copy](https://developer.mozilla.org/en-US/docs/Web/API/Element/copy_event), 
    [paste](https://developer.mozilla.org/en-US/docs/Web/API/Element/paste_event)
  * select input events: [change](https://developer.mozilla.org/en-US/docs/Web/Events/change)
  * [DOMContentLoaded](https://developer.mozilla.org/en-US/docs/Web/API/Window/DOMContentLoaded_event) vs 
    [load](https://developer.mozilla.org/en-US/docs/Web/API/Window/load_event)
  * [custom events](https://developer.mozilla.org/en-US/docs/Web/Guide/Events/Creating_and_triggering_events) 
    can be useful, e.g. to provide API of [Web-component](https://developer.mozilla.org/en-US/docs/Web/Web_Components)
* [Event.preventDefault()](https://developer.mozilla.org/en-US/docs/Web/API/Event/preventDefault#Blocking_default_click_handling) 
  to prevent default behaviour
* [Event.target](https://developer.mozilla.org/en-US/docs/Web/API/Event/target) 
  is a reference to the object that dispatched the event
* Coords event relative to the window: 
  [MouseEvent.clientY](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/clientY) / 
  [clientX](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/clientX)
* Other properties: [Event.type](https://developer.mozilla.org/en-US/docs/Web/API/Event/type), 
  [Event.timeStamp](https://developer.mozilla.org/en-US/docs/Web/API/Event/timeStamp)
* [Event bubbling (vs capturing)](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events#Event_bubbling_and_capture)
* [Event.stopPropagation()](https://developer.mozilla.org/en-US/docs/Web/API/Event/stopPropagation) : 
  prevent further bubbling
* [Event delegation](https://davidwalsh.name/event-delegate) : 
  event listener on parent that catch events on childs
  * [Event.target](https://developer.mozilla.org/en-US/docs/Web/API/Event/target) vs 
    [Event.currentTarget](https://developer.mozilla.org/en-US/docs/Web/API/Event/currentTarget)
* [Event.bubbles](https://developer.mozilla.org/en-US/docs/Web/API/Event/bubbles): 
  read-only property to indicate if bubbling happen

[*Go to top*](#Web-APIs)
