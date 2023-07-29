---
title: Coding Standards (2019)
---
**The House Before The Drapes**

Outcomes before inputs. Process before pages. Layout before colorscheme.
Architecture before details. [Ask why five
times](https://expertprogrammanagement.com/2019/05/the-5-whys/). Think and plan
for the overall goals of a system or project, then think of how each audience
will accomplish those goals. That should inform your interface whether it is a
graphical user interface or just a single new button. Then look at how to make
it well integrated and visually appealing. And being visually appealing does
matter, because user experience is influenced by their attraction and comfort
with the interface, which affects their effeciency with the tool.

**Convention Over Configuration**

Attempt to keep systems as consistent as possible by allowing the most limited
number of customizations necessary to achieve the outcome. This does mean that
[conventions](https://en.wikipedia.org/wiki/Convention_over_configuration)
should be decided ahead of time to accomodate the real needs of users to track
and evaluate different specific scenarios, but single audience customizations
should be critiqued on the basis of legal/program requirements and effort to
implement first.

**Don't Reinvent the Wheel**

When possible prefer frameworks and packages that are widely used, supported,
and tested. No matter your language or system, someone has created a calendar
for it already. No matter what you're working with, there is a way to handle
validations you can implement. Let your work be focused on the processes that
achieve the specific goals of the system, not the general goals of any system.
As much as possible, keep using the same frameworks so that you can build
mastery of a common set of tools. However don't be afraid to look at new
frameworks to see where they might be superior or a better fit - or if they have
good ideas you can steal.

**Control Your Code**

Filenames with -v2 is not version control. Using a version control system backs
up your code, let's you branch to experiment, selectively return to earlier code
choices, and work in teams without overwriting each other. Version control data
can be profiled to understand the overall picture of change in systems, ways it
has grown and changed, which helps in planning next steps and time allotment for
work to be done. Also, by forcing certain working habits it makes it harder for
bad/rushed choices to be made, and easier to be recovered from.

**Gotta Keep 'Em Separated**

Keep in mind a [separation of
concerns](https://en.wikipedia.org/wiki/Separation_of_concerns) - data and code
should be separate and independent. Specific record references should not be
hard-coded into the project itself, but instead identified using flags or
conditions stored on the record itself. For instance, if trying to make an
exception for a child who only reads books upside down you shouldn't code
if(Child.Id equals 100) then..., instead describe the condition on the Child
record and test that with if(Child.readsUpsideDown equals true) then.... Doing
this prevents having to search code when record values change, and allows for
the possibility of more than one record needing that requirement in the future.
This also means that if data needs to be migrated or updated it will not break
existing code, and vice versa. Code should deal with properties of data, not
particular data. Another way to sum it up is to say data should reflect meaning,
code should only reflect process.

**One Thing At A Time**

When tracking information, the entities being processed should be
[normalized](https://oracle-surya.blogspot.com/2012/05/normalization-with-example.html)
down to their constiuent independent parts. If something is likely to change
year after year, or can/does exist independently of an aspect of its definition,
it should likely be stored as its own record then related back to the unchanging
part. For instance, a child may participate in a classroom program, but the
child and classroom will likely exist after the program has ended for the year.
So there should be a separate record for the child's personal information, a
record for the classroom itself, and a record for the relationship between the
child and the classroom with the details of that years experience. This also
holds for properties of an entity. If a child's parent's give consent to be
texted, the consent and the phone number should be stored separately, rather
than relying on the presence of the phone number to imply consent. This will
help the record be more tolerant to changing processes and more intuitively
represent something in the real world in the data structures of the program.

Similarly functions and processes should do a minimal amount of data change,
instead favor multiple smaller functions that can be chained to change data in
sequence. This will help with troubleshooting as issues can be identified more
clearly, and code can be reused more easily.

**Explicit Is Better Implicit**

Similarly, any data, status, or process should spell out what it is and what it
means. Data itself (whether in variables or in a database) should be clearly
labelled, and ideally calculated fields or columns should be present to define
conditional compound values, rather than relying on if/else's in the code. This
is obviously not always possible, but as much as it is it is better to have all
meaningful information present where the data is stored rather than relying on
later interpretation by code. Specifically in Salesforce and MySQL a formula can
be implemented to combine other data values so that the conditional value is
clear. Instead of creating a script that says if(ConsentTexting and
ConsentMedia) then... you can create a formula/generated field called ConsentAll
that equals (ConsentTexting and ConsentMedia) and then test ConsentAll in the
code. That way you have just one place to check in the future if other forms of
Consent need to be checked. Again, this isn't always possible, but a good
practice if you can.

**Clear Names Full Words, Can't Lose**

No acronyms. Minimal jargon. Whole words. Assume a [beginners
mind](https://en.wikipedia.org/wiki/Shoshin). Not only will you reduce your own
cognitive load in developing, but you will make it far easier for new people to
support or use your project. Resist the temptation of "everyone knows what this
means" in anything less than national or international standards, because you
are building not just for the people we already have, but people who have not
yet joined.

**CamelCase or under_score but nothing more**

All code from variables to function names should be in written CamelCase or
under_score and should be consistent across the system/project. The only time to
switch standards is when a character limit is imposed in some way to prevent
being consistent, as in the case when you are using under_score but run out of
room naming a field. You should try to use the same naming scheme as the system
you are working in, such as how Salesforce uses under_score for most of its
fieldnames.

**DRY Up Your Code**

[Don't Repeat Yourself](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself).
If you notice a significant chunk of very similar code repeating, it is probably
a good idea to make that a function on its own and call it where it shows up.
That may mean generalizing a small part and calling it with a parameter. This
helps reduce overall code size which increases readability and manageability. It
also allows for easier updates, bug fixes, and building new features - less
code, less to debug. [Balance matters
though](https://stackoverflow.com/a/11837973) - don't try to DRY two or three
lines of code on their own and don't DRY to the detriment of clarity and
readability.

**Reduce, Reuse, Recycle**

It isn't just good for the environment. Write your code in such a way that you
might be able to use it again, either within the same project or in another. By
using processes that focus on small data changes at a time (reducing) and moving
repeated code to their own modules (reusing) you can recycle that code and not
only save time but prevent new bugs coming up in new code.

**Don't Optimize Prematurely, But Optimize**

Trying to [optimize too
soon](https://en.wikipedia.org/wiki/Program_optimization#When_to_optimize) can
lead to getting stuck in development loops. A little like an author retooling a
paragraph over and over, they might never finish the book. It is better to plow
through, get the minimum viable product out and then optimize. And you should
optimize, to be sure - but doing it too soon may make you optimize a pattern you
actually don't use very frequently, while missing a larger pattern that you
can't see until the project is more complete.

**The Principle of Least Privilege**

At all times [the minimum amount of data
access](https://en.wikipedia.org/wiki/Principle_of_least_privilege) should be
observed. We may not be able to imagine any of our people doing something
malicious, but security is not about what we can imagine - it is about what we
haven't even guessed. Accidents happen, accounts are subverted, and people get
angry - security is just making sure that no matter the cause, information stays
safe. Good security is not a pair of handcuffs on users, it is an umbrella over
their heads. Identifiying exactly what people need access to for their role
helps simplify their experience and reduce the possibility of accidents. In this
way reducing access is actually increasing ease and comfort of use.

**Validation Isn't Just For Feelings**

Data should always be [validated
twice](https://softwareengineering.stackexchange.com/questions/341913/should-a-backend-restful-api-implement-data-validation)
- once on the front end to serve the user and help them have a better and more
confident experience, and once on the back end to ensure the data is sane and
accurate. Front-end validation should display specific warnings, ideal located
on the fields that the issue exists on. Things like valid date ranges, sane
number scales, and field length should be implement along with data type checks
(numbers for numbers, text for text) and required fields. Things like
placeholder values or below the field help text are great to assist the user in
getting it right the first time. As you consider process and layout, think, "How
can I help prevent users from doing something by accident?"

On the back end data should be santitized (cleared of potentially problematic
data) and validated again. It is possible in most systems for data to come in
from multiple points of entry, some of which (like a web form) can be easily
manipulated or corrupted. Back end validations are much like implicit data -
best implemented where the data is stored. MySQL column valdiations and
Salesforce record validations help make sure that the very last step in the
process before being saved is a validation. Errors when validations fail on the
back end must be bubbled up to the front end so that the user or program has a
chance to react to it, at a minimum informing the user data was not saved.

**On Error Cause Terror**

Processes and validations should never fail silenty. An error should strongly
draw the users attention and raise a flag that something needs to be dealt with.
Errors must be [handled](https://en.wikipedia.org/wiki/Exception_handling),
whether that is a front-end message that just says "Error, contact system
administrator" or a more complete handler for something that is user fixable.
Most functions should use some variety of
[try/catch](https://en.wikipedia.org/wiki/Exception_handling_syntax) processing
to allow users to understand what has happened to their data. If it is something
they can fix, like a data validation failure, then the interface should give
them that option without reloading the page or losing their current state. If it
is an issue they cannot fix, then ideally it should notify the appropriate
support staff automatically with a well defined error message, or else give them
the data to pass on a detailed error report.

**Lovely Little Layout Logic**

-   [Visual breathing
room](https://en.wikipedia.org/wiki/White_space_(visual_arts)) not dead
space

-   Big text is better than small text

-   Respect muscle memory

-   Once drawn on screen don't move

-   [Mobile
First](https://medium.com/@Vincentxia77/what-is-mobile-first-design-why-its-important-how-to-make-it-7d3cf2e29d00)
but only for mobile things

-   Consistent colors for similar subjects

-   Apply Occam's Razor: "Entities should not be multiplied without necessity" -
show only what the user needs to accomplish the system's goal

**Dance Like Nobody's Watching, Code Like Everyone Is**

Keep in mind that it is very likely someone else will need to read what you have
written, follow your logic, and understand your goals. Use comments like salt -
sprinkle on to enhance, but don't overdo it. When possible have others
immediately look at your code and give you feedback on what makes sense, and
what doesn't. Don't be afraid to use other people as a [rubber
duck](https://en.wikipedia.org/wiki/Rubber_duck_debugging) - and even better,
then can talk back. Keep even your future self in mind, who will surely read
present-you's code and say "What were you thinking?!"

**Context Switching Costs Something**

When working on any project, give yourself time and space to really focus.
Programming is not a discrete action like answering an email or finishing a
form. It requires a continuous effort to think through a complicated system from
end to end. Entities, relationships, processes, and audiences are all a part of
every step of programming, and every time you have to take your mind out of that
flow you lose momentum. When asked to do something else, the effort to complete
the request may be very small, but the cost of having to clear your mind of one
set of information, load another, and then switch back is huge. [Multitasking is
a
myth](https://www.psychologytoday.com/us/blog/creativity-without-borders/201405/the-myth-multitasking)
- the human brain doesn't actually multitask as we commonly think of it. What we
do is juggle contexts, and like most juggling it is difficult and often ends up
with someone dropping the ball. Give yourself time, and protect the time to get
your task done - it actually benefits even someone with "a quick question".