# Current Development Goals:

## Accessibility

### Answer Box
Currently aiming to work on answer box code to support accessibility.
Working on this with Jeffrey Kuan, who is the actual accessibility expert.

Current Development Goals/Path:
1) Get the answer box to emit arbitrary (placeholder) html code at states:
   * Empty / Awaiting interaction.
   * Answer Entered and Submitted, but Not Understood (e.g. "parsing error").
   * Answer Validated as Incorrect.
   * Answer Validated as Correct.
2) Get intended html code from Jeffrey Kuan for the four states above.
3) Ensure the html is processed by screen readers (and anything else as per Kuan)
    correctly and that the answer box is detected and interfaced with correctly.
4) Add any necessary intent command/tag for custom author text.
    * intent command will be its own development, likely done in tandem. See below.
5) Test all changes against the test reposotiroy for unexpected behavior/bugs.
6) Fix anything needed, then contact Bart/Wim for additional testing against OSU/KL Servers.
7) Fix anything from previous step, then repeat step 6 as needed.
8) Ensure all features, intended use, best-practices, etc are fully documented.
9) Ensure DTX file compiles correctly into package via make and last pass for bugs or missing documentation.
10) Submit to production code.


### `\intent` command
The current accessibility plan is to (among other things) create a `\intent` command that
will allow instructors to inject custom text that is read by a screen reader (maybe other
things, as per Kuan?) but doesn't otherwise appear on the screen. This will be done in
html, and is indended to be used to supplement accessibility information provided to
screen readers et al. 

Current Development Goals/Path:
1) Make a `\intent` command that emits arbitrary (placeholder) html code.
2) Get intended html code from Jeffrey Kuan for actual device integration.
    * i.e. get code that exposes the html to an accessibility device, but not a screen.
3) Ensure the html is processed by accessibility devices correctly. Some Examples:
    * Text must be parsed correctly as text.
    * Math must be parsed as math, and emited in a sane fashion (understandable equations etc).
    * `\intent` contents must be processed at the correct time/place in page processing
        - Including things like nested content
        - Unveiled/Hidden content (e.g. nested problem scaffolding)
        - Expanded/Not-Expanded content
        - Consecutive `\intent` commands (e.g. conditionals for followup `\intent`s). 
4) Debug and revise as needed from step 3 repeatedly (this is likely to take a while).
5) Test all changes against the test reposotiroy for unexpected behavior/bugs.
6) Fix anything needed, then contact Bart/Wim for additional testing against OSU/KL Servers.
7) Fix anything from previous step, then repeat step 6 as needed.
8) Ensure all features, intended use, best-practices, etc are fully documented.
9) Ensure DTX file compiles correctly into package via make and last pass for bugs or missing documentation.
10) Submit to production code.

