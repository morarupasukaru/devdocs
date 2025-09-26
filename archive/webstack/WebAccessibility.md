# Web Accessibility

Web Accessibility (A11y) means that websites are accessible to everyone regardless of disability. 

* Concepts
  * [Accessibility, Usability, and Inclusion](https://www.w3.org/WAI/fundamentals/accessibility-usability-inclusion/)
    are closely related aspects in creating a web that works for everyone
  * [Accessibility](https://www.w3.org/WAI/fundamentals/accessibility-intro/) focus on people with disabilities
  * Accessibility is related to _user experience_, _usability_, and _user-centered design_
  * [How People with Disabilities Use the Web?](https://www.w3.org/WAI/people-use-web/)
    * _Assistive Technologies_ refer to hardware or software that enable people with disabilities to interact and engage with the digital environment e.g. using a screen reader or a switch control.
    * _Adaptive Strategies_ are techniques that people with disabilities use to interact with the digital environment such as adjusting platform and browser settings or resizing browser windows.
  * [Accessibility perspectives](https://www.w3.org/WAI/perspective-videos/)
    * [Keyboard Compatibility](https://www.w3.org/WAI/perspective-videos/keyboard/)
    * [Colors with Good Contrast](https://www.w3.org/WAI/perspective-videos/contrast/)
    * [Clear Layout and Design](https://www.w3.org/WAI/perspective-videos/layout/)
    * [Text to Speech](https://www.w3.org/WAI/perspective-videos/speech/)
    * [Large Links, Buttons, and Controls](https://www.w3.org/WAI/perspective-videos/controls/)
    * [Video Captions](https://www.w3.org/WAI/perspective-videos/captions/)
    * [Customizable Text](https://www.w3.org/WAI/perspective-videos/customizable/)
    * [Speech Recognition](https://www.w3.org/WAI/perspective-videos/voice/)
    * [Understandable Content](https://www.w3.org/WAI/perspective-videos/understandable/)
    * [Notifications and Feedback](https://www.w3.org/WAI/perspective-videos/notifications/)
  * [Accessibility Guidelines](https://www.w3.org/WAI/standards-guidelines/) 
    provided by [WAI (Web Accessibility Initiative)](https://www.w3.org/WAI/) like ...
    * [Web Content Accessibility Guidelines (WCAG)](https://www.w3.org/WAI/standards-guidelines/wcag/glance/) 
      to make accessible websites
    * [Accessible Rich Internet Applications (ARIA)](https://www.w3.org/WAI/standards-guidelines/aria/)
      to make accessible rich applications/user components
  * [Web Content Accessibility Guidelines (WCAG)](https://www.w3.org/WAI/standards-guidelines/wcag/glance/) principles:
    * [Perceivable](https://www.w3.org/WAI/fundamentals/accessibility-principles/#perceivable): 
      Information can be presented in different ways; for example, in braille, different text sizes, text-to-speech, or symbols, etc.
    * [Operable](https://www.w3.org/WAI/fundamentals/accessibility-principles/#operable): 
      Functionality can be used in different modalities; for example, keyboard, mouse, sip-and-puff, speech input, touch, etc.
    * [Understandable](https://www.w3.org/WAI/fundamentals/accessibility-principles/#understandable): 
      Information and functionality is understandable; for example consistent navigation, simple language, etc.
    * [Robust](https://www.w3.org/WAI/fundamentals/accessibility-principles/#robust): 
      Content can be interpreted reliably by a wide variety of browsers, media players, and assistive technologies.
* [WAI](https://www.w3.org/WAI/) documentations for development
  * [Introduction to Web Accessibility](https://www.w3.org/WAI/fundamentals/accessibility-intro/)
  * [Initial checks/review](https://www.w3.org/WAI/test-evaluate/preliminary/) to 
    [test & evaluate](https://www.w3.org/WAI/test-evaluate/) a website
  * Tips for [developing](https://www.w3.org/WAI/tips/developing/),
    for [designing](https://www.w3.org/WAI/tips/designing/),
    for [writing](https://www.w3.org/WAI/tips/writing/)
    (and for [customizing your computer](https://www.w3.org/WAI/meta/customize/))
    * [Use Clear and Understandable Content](https://www.w3.org/WAI/WCAG2/supplemental/objectives/o3-clear-content/)
  * [Tutorials about Design & Develop](https://www.w3.org/WAI/tutorials/)
  * [Practices Guide](https://www.w3.org/WAI/ARIA/apg/)
    for [ARIA](https://www.w3.org/WAI/standards-guidelines/aria/)
    * see also [Read Me First](https://www.w3.org/WAI/ARIA/apg/practices/read-me-first/) practises
* Tips
  * use [skip links](https://webaim.org/techniques/skipnav/), see also [removing headaches from focus management](https://developer.chrome.com/blog/focus-start-point/)
  * [roving tabindex for managing focus within the radio group](https://www.w3.org/WAI/ARIA/apg/patterns/radio/examples/radio/)
  * [Document.activeElement](https://developer.mozilla.org/en-US/docs/Web/API/Document/activeElement) returns the Element within the DOM that currently has focus.
* Other documentations
  * [Accessibility in Angular](https://angular.io/guide/accessibility)
  * [Accessibility on MDN web docs](https://developer.mozilla.org/en-US/docs/Learn/Accessibility)
  * [Introduction to ARIA - Accessible Rich Internet Applications](https://webaim.org/techniques/aria/)
  * [Designing for accessibility is not that hard](https://uxdesign.cc/designing-for-accessibility-is-not-that-hard-c04cc4779d94)
  * [Web Accessibility](https://www.udacity.com/course/web-accessibility--ud891) google course
    or [text version](https://web.dev/accessibility/)
  * [Digital Accessibility Foundations](https://www.w3.org/WAI/courses/foundations-course/) WAI course
* Tools  
  * [How to Meet WCAG (Quick Reference)](https://www.w3.org/WAI/WCAG21/quickref/)
     or [WCAG 2 Checklist](https://webaim.org/standards/wcag/checklist)
  * [WAVE (Web Accessibility Evaluation Tool)](https://wave.webaim.org/)
  * [Lighthouse](https://developers.google.com/web/tools/lighthouse/) to audit accessibilty (and performance, spa, etc. of a website)
    * [unlighthouse](https://unlighthouse.dev/) to scan your entire site with Google Lighthouse
  * [Firefox Accessibility Inspector](https://developer.mozilla.org/en-US/docs/Tools/Accessibility_inspector)
  * [NVDA](https://www.unimelb.edu.au/accessibility/tools/testing-web-pages-with-nvda) screen reader for Windows
  * [Apple VoiceOver](https://www.apple.com/accessibility/vision/) screen reader for Apple
  * [Colour Contrast Analyser](https://developer.paciellogroup.com/color-contrast-checker/)
  * see also [tools recommanded by CivicActions](https://accessibility.civicactions.com/guide/tools) and [Web Accessibility Evaluation Tools List](https://www.w3.org/WAI/ER/tools/)

[*Go to parent page*](README.md)

*(Page mainly written in 06.2023; links checked on 19.02.2024)*
