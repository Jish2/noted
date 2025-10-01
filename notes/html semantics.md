---
created: 2024-12-27T23:13
updated: 2024-12-28T12:48
---
#language/html
[1^]: [HTML semantics cheat sheet · Web Dev Topics · Learn the Web](https://learntheweb.courses/topics/html-semantics-cheat-sheet/)
- Document
- Lists
- Text
- Images & media
- Data & code
- Meaningless tags
- Be careful
- Links
- Date/time formats

## Document

- `<title>`
  - Second most important piece of content.
  - Shown in the browser tab & search results.
  - Should be unique for *every* page on the site.
- `<link href="…" rel="stylesheet">`
  - For linking CSS and other resources like feeds.
  - `href` is the path the file.
  - `rel` has different values for other resources.
- `<header>`
  - When inside `<body>` it’s the website masthead.
  - When inside `<article>` it’s the most important information.
- `<footer>`
  - When inside `<body>` it’s the website footer.
  - When inside `<article>` it’s the least important information.
- `<main>`
  - Primary content of the page.
- `<nav>`
  - Defines a group a navigation links.
- `<article>`
  - A piece of content that’s independent.
  - Could be removed from this website and still make sense.
- `<section>`
  - A group in a series of related content pieces.
- `<aside>`
  - Secondary content not required to understand the main content.
- _CSS link tag_

  ```html
  <link href="css/main.css" rel="stylesheet" />
  ```

- _Navigation inside header_
  ```html
  <header>
  	<nav>
  		<ul>
  			<li><a href="#">Stegosaurus</a></li>
  			<li><a href="#">Triceratops</a></li>
  			<li><a href="#">Ankylosaurus</a></li>
  		</ul>
  	</nav>
  </header>
  ```
- _Main content groups_

  ```html
  <body>
  	<header>
  		<nav>…</nav>
  	</header>

  	<main>
  		<h1>Dinos-R-Us</h1>
  	</main>

  	<footer>
  		<p>© 2063 Dinos-R-Us</p>
  	</footer>
  </body>
  ```

## Lists

- `<ul>`
  - An unordered list—the order of items isn’t important.
  - Can only have `<li>` elements as direct children.
- `<ol>`
  - An ordered list—the order of the items is important.
  - Could be alphabetical, numerical, best to worst, etc.
  - Can only have `<li>` elements as direct children.
- `<li>`
  - A single list item.
  - Must be inside a `<ul>`, `<ol>` or `<menu>`.
  - Can have most other elements inside it.
- `<dl>`
  - A description list—a grouping of terms and definitions.
  - Words & definitions, titles & summaries, data points, etc.
  - Can only have `<dt>` and `<dd>` elements as direct children.
- `<dt>`
  - Description title, the term of the item.
  - Must come before the `<dd>`.
- `<dd>`
  - Description definition, the data, or text of the item.
  - Can be multiple `<dd>` tags underneath one `<dt>`.
- _Unordered list_
  ```html
  <ul>
  	<li>Tyrannosaurus</li>
  	<li>Spinosaurus</li>
  	<li>Velociraptor</li>
  </ul>
  ```
- _Ordered list_
  ```html
  <ol>
  	<li>Mercury</li>
  	<li>Venus</li>
  	<li>Earth</li>
  	<li>Mars</li>
  </ol>
  ```
- _Description list_
  ```html
  <dl>
  	<dt>Length</dt>
  	<dd>2.3 m</dd>
  	<dt>Weight</dt>
  	<dd>4 tonnes</dd>
  </dl>
  ```
- `<menu>`
  - For semantically marking up a web application’s toolbar of buttons.
  - The `<menu>` tag also uses `<li>` tags inside—one for each toolbar button.
  - You may still have to remove the bullets.
- _Menu toolbar list_
  ```html
  <menu>
  	<li><button>Like</button></li>
  	<li><button>Share</button></li>
  	<li><button>Comment</button></li>
  </menu>
  ```

## Text

- `<a href="…">`
  - For making hyperlinks.
  - `href` is the path to where the link should go.
- `<h1>`
  - The *most* important piece of content on the page.
  - On the homepage this should be the company’s name.
  - On inside pages this should be the page title.
- `<h2>`, `<h3>`, `<h4>`, `<h5>`, `<h6>`
  - Content headings, each a sub-heading of the one above.
  - The `<h2>` is a sub-heading of `<h1>`, `<h3>` a sub-heading of `<h2>`, etc.
- `<hgroup>`
  - Allows you to group multiple headings together and have them semantically treated as a single heading.
  - It’s primary purpose is for subheadings.
- `<p>`
  - A generic paragraph of text.
- `<blockquote>`
  - A large, stand alone quote from another source.
- `<cite>`
  - A citation for another source, often used with quotations.
  - A person’s name, a URL, a book, a movie title, etc.
- `<q>`
  - A small quotation embedded within other content.
- `<em>`
  - A string of emphasized, slightly more important text.
  - Screen readers will change their voice for this text.
- `<strong>`
  - A string of highly emphasized, much more important text.
  - Screen readers will change their voice for this text.
- `<ins datetime="…">`
  - Content that was inserted after the document was published.
  - `datetime` defines when it was added.
- `<del datetime="…">`
  - Content that was deleted after the document was published.
  - `datetime` defines when it was removed.
- `<abbr title="…">`
  - An acronym or abbreviation, like “HTML”, “CSS”, etc.
  - `title` contains the expanded version, like “Hypertext Markup Language”.
- `<dfn>`
  - A definition of a term on the page.
  - Should only be used once of the term.
- `<mark>`
  - Used to highlight a piece of text for reference.
  - The keywords in a search results page, the current navigation item.
- `<i>`
  - Defines technical term, a ship name, a book title, a thought, sarcasm, another language.
- `<b>`
  - Defines a keyword, like product name in a review, a lead sentence in a paragraph.
- `<s>`
  - Content that’s no longer relevant to the document.
  - Consider if the `<del>` element is better suited first.
- `<u>`
  - Labels the text as having a non-textual annotation.
  - A misspelled word, a Chinese proper name, etc.
- `<small>`
  - Represents side comments and fine print.
- `<address>`
  - Contact information, email, tel, postal address, etc.
- _Blockquotes_
  ```html
  <blockquote>
  	<p>Dinosaurs may be extinct from the face of the planet, but they are alive and well in our imaginations.</p>
  	<footer>— <cite>Steve Miller</cite></footer>
  </blockquote>
  ```
- _Addresses_
  ```html
  <address>
  	Jet Propulsion Laboratory
  	<br />4800 Oak Grove Drive <br />Pasadena, California <br />91109
  </address>
  ```
- _Text edits_
  ```html
  <p>Launchpad 39A owned by <del datetime="2014-04-14">NASA</del> <ins datetime="2014-04-14">SpaceX</ins></p>
  ```
- _Heading groups_
  ```html
  <hgroup>
  	<h1>Star Wars</h1>
  	<h2>The Empire Strikes Back</h2>
  </hgroup>
  ```
- _Abbreviations_
  ```html
  <abbr title="Star Trek: The Wrath of Khan">ST:TWOK</abbr>
  ```
- _Other languages_
  ```html
  <i lang="fr">Bonjour</i>
  ```

## Images & media

- `<img src="…" alt="…">`
  - Embeds an image that’s important to the content.
  - `src` is a path to the image file.
  - `alt` describes the image if it cannot be seen.
- `<figure>`
  - Embeds annotated images, illustrations, photos, code, etc.
  - Could be moved out of place and would still make sense.
- `<figcaption>`
  - For adding a caption/annotation to the `<figure>`.
  - Must be inside a `<figure>` element—cannot stand alone.
- `<picture>`
  - Responsive image insertion—allows developers to provide different images for different contexts.
- `<video poster="…" autoplay loop muted controls>`
  - For embedding movies into a website.
  - `poster` is the path to an image that’s displayed before the video plays.
  - `autoplay` will hint the video to start automatically.
  - `loop` triggers whether the video should repeat or not.
  - `muted` can be added to not play sound by default.
  - `controls` shows or hides the browser’s player buttons.
- `<audio autoplay loop muted controls>`
  - For embedding sounds into a website.
  - `autoplay` will hint the audio to start automatically.
  - `loop` triggers whether the audio should repeat or not.
  - `muted` can be added to not play sound by default.
  - `controls` shows or hides the browser’s player buttons.
- `<source>`
  - Must be inside `<picture>`, `<video>` or `<audio>` to define the different versions of content.
  - For example, in video it gives paths to the MP4 and WEBM formats.
- `<track>`

  - Used to pair captions, chapters, etc. with `<video>`elements.

- _Basic images_
  ```html
  <img src="images/dino.jpg" alt="An beautiful, long-necked Brontosaurus" />
  ```
- _Figures & captions_
  - Use only if there’s a caption.
  ```html
  <figure>
  	<img src="images/dino-small.jpg" alt="" />
  	<figcaption>So many dinosaurs I can’t even count!</figcaption>
  </figure>
  ```
- _Responsive images_
  - See [Responsive & retina images for details](https://learntheweb.courses/topics/responsive-retina-images/).
  ```html
  <picture>
  	<source media="(min-width: 60em)" srcset="images/dino-wide.jpg" />
  	<source media="(min-width: 38em)" srcset="images/dino-rectangle.jpg" />
  	<img src="images/dino-small.jpg" alt="All the dinosaurs!" />
  </picture>
  ```

## Data & code

- `<sub>`
  - Defines text as being subscript.
- `<sup>`
  - Defines text as being superscript.
- `<var>`
  - Represents a variable in math or programming.
- `<time datetime="…">`
  - Marks some text as a time or date.
  - `datetime` defines the machine readable version.
- `<data value="…">`
  - Marks elements as being a numerical piece of information.
  - `value` provides the machine readable version.
- `<meter value="…" min="…" max="…">`
  - Represents a single number in a range of numbers.
  - `value` is the current number.
  - `min` is the minimum number.
  - `max` is the maximum number.
- `<progress value="…" min="…" max="…">`
  - Represents the current position in a series of steps.
  - `value` is the current position.
  - `min` is the minimum position.
  - `max` is the maximum position.
- `<code>`
  - Defines a piece of text as a code sample.
- `<pre>`
  - A piece of text that has a specific formatting, where tabs, whitespaces, etc. should be maintained.
- `<kbd>`
  - Something a user should type into their computer.
- `<samp>`

  - Something a user should see output from a computer.

- _Time_
  ```html
  Apollo 11 landed on the moon <time datetime="1969-07-20T20:18">July 20, 1969</time>
  ```
- _Data_
  ```html
  Argentinosaurus weighted approximately <data value="90">90 tonnes</data>
  ```
- _Maths_
  ```html
  E = mc<sup>2</sup>
  ```

## Meaningless tags

- `<div>`
  - Inherits meaning from its children.
  - Divides content into logical groups, when no other tag is better suited.
  - Has restrictions on what elements it can be inside.
- `<span>`
  - Inherits meaning from its children.

## Be careful

- `<br>`
  - Creates a line break that’s significant to the content.
  - Useful in poems and addresses where the division of lines is important.
  - _Do not use to create space in a design—use margins and padding._
- `<hr>`
  - Represents a thematic break in the content.
  - For example, a scene change or topic change.
  - _Do not use to create a horizontal line—use CSS borders._
- `<button>`
  - Represents a interactive, clickable button.
  - Should be used in forms and with JavaScript.
  - _Do not use to link to another page—use the `<a>` tag._
- `<wbr>`
  - Presents an opportunity for the browser to add a line-break if necessary.
  - Groups strings of text, when no other tag is better suited.

## Links

- _Links that go nowhere_
  - The `href` always needs a value—`#` means nowhere.
  ```html
  <a href="#">Nowhere</a>
  ```
- _Links on the same page_

  - Add an `id=""` to the element to jump to, refer to that inside the `href`

  ```html
  <a href="#herbivores">See the herbivores</a>

  <h2 id="herbivores">Herbivores</h2>
  ```

- _Links to other files_

  - Just write the name of the HTML file, also include any folders its inside.

  ```html
  <a href="dinos.html">Dinosaurs</a>

  <!-- or in another folder -->
  <a href="herbivores/stegosaurus.html">Stegosaurus</a>
  ```

- _Links to other websites_

  - Always start with `https://` or less ideally `http://`

  ```html
  <a href="https://www.wikipedia.org/">Wikipedia</a>

  <!-- Adding `rel="external"` for outward-bound sites is good -->
  <a href="https://www.wikipedia.org/" rel="external">Wikipedia</a>
  ```

- _Links to phone numbers_

  - Start with `tel:`, use international format

  ```html
  <a href="tel:+18005552368">Call Me!</a>
  ```

  - Also send a text message with `sms:`

  ```html
  <a href="sms:+18005552368&body=Who%20ya%20gonna%20call">Call Me!</a>

  <!-- or without a default number -->
  <a href="sms:&body=Who%20ya%20gonna%20call">Call Me!</a>
  ```

- _Links to email addresses_

  - Pops open a new email message, start with `mailto:`

  ```html
  <a href="mailto:hey@thomasjbradley.ca">Thomas</a>

  <!-- Add a subject too -->
  <a href="mailto:hey@thomasjbradley.ca?subject=How%20are%20you?">Thomas</a>

  <!-- Even a default body -->
  <a href="mailto:hey@thomasjbradley.ca?subject=How%20are%20you?&body=Hey%20Thomas">Thomas</a>
  ```

  - `%20` is used to escape spaces—[See more percent-encoding examples](https://en.wikipedia.org/wiki/Percent-encoding)

## Date/time formats

Apply to the `datetime=""` attribute of the `<time>`, `<del>` & `<ins>` elements.

- _Year_
  - Format: `YYYY`
  - Example: `1963`
- _Year, month_
  - Format: `YYYY-MM`
  - Example: `1963-11`
  - _Nov. 1963_
- _Year, month, day_
  - Format: `YYYY-MM-DD`
  - Example: `1963-11-23`
  - _Nov. 23, 1963_
- _Year, week_
  - Format: `YYYY-Wdd`
  - Example: `1963-W47`
  - _1936, the week of Nov. 18–24_
- _Hour, minute_
  - Format: `HH:MM`
  - Example: `17:16`
  - _5:16 PM_
- _Hour, minute, second_
  - Format: `HH:MM:SS`
  - Example: `17:16:20`
  - _5:16:20 PM_
- _Hour, minute, second, millisecond_
  - Format: `HH:MM:SS.sss`
  - Example: `17:16:20.258`
  - _5:16:20.258 PM_
- _UTC timezone_
  - Format: `Z`
  - Example: `Z`
  - _UTC timezone_
- _Timezone offsets_
  - Format: `±HH:MM`
  - Example: `-05:00`
  - _Eastern Standard Time, Daylight Savings_
- _Year, month, day, hour, minute_
  - Format: `YYYY-MM-DDTHH:MM`
  - Example: `1963-11-23T17:16`
  - _Nov. 23, 1963 at 5:16 PM_
- _Year, month, day, hour, minute, second_
  - Format: `YYYY-MM-DDTHH:MM:SS`
  - Example: `1963-11-23T17:16:20`
  - _Nov. 23, 1963 at 5:16:20 PM_
- _Year, month, day, hour, minute, second, millisecond_
  - Format: `YYYY-MM-DDTHH:MM:SS.sss`
  - Example: `1963-11-23T17:16:20.258`
  - _Nov. 23, 1963 at 5:16:20.258 PM_
- _Year, month, day, hour, minute, UTC_
  - Format: `YYYY-MM-DDTHH:MMZ`
  - Example: `1963-11-23T17:16Z`
  - _Nov. 23, 1963 at 5:16 PM UTC_
- _Year, month, day, hour, minute, timezone_
  - Format: `YYYY-MM-DDTHH:MM±HH:MM`
  - Example: `1963-11-23T12:16-05:00`
  - _Nov. 23, 1963 at 12:16 AM EST_
- _Year, month, day, hour, minute, second, timezone_
  - Format: `YYYY-MM-DDTHH:MM:SS±HH:MM`
  - Example: `1963-11-23T12:16:20-05:00`
  - _Nov. 23, 1963 at 12:16:20 AM EST_
- _Year, month, day, hour, minute, second, millisecond, timezone_
  - Format: `YYYY-MM-DDTHH:MM:SS.sss±HH:MM`
  - Example: `1963-11-23T12:16:20.258-05:00`
  - _Nov. 23, 1963 at 12:16:20.258 AM EST_
- _Period of days_
  - Format: `PddD`
  - Example: `P686D`
  - _686 days_
- _Period of days, hours_
  - Format: `PddDThhH`
  - Example: `P686DT23H`
  - _686 days, 23 hours_
- _Period of days, hours, minutes_
  - Format: `PddDThhHmmM`
  - Example: `P686DT23H18M`
  - _686 days, 23 hours, 18 minutes_
- _Period of days, hours, minutes, seconds_
  - Format: `PddDThhHmmMssS`
  - Example: `P686DT23H18M14S`
  - _686 days, 23 hours, 18 minutes, 14 seconds_
- _Period of days, hours, minutes, seconds, milliseconds_
  - Format: `PddDThhHmmMss.sssS`
  - Example: `P686DT23H18M14.400S`
  - _686 days, 23 hours, 18 minutes, 14 seconds, 400 milliseconds_
- _Period of hours_
  - Format: `PThhH`
  - Example: `PT23H`
  - _23 hours_
- _Period of minutes_
  - Format: `PTmmM`
  - Example: `PT18M`
  - _18 minutes_
- _Period of minutes, seconds_
  - Format: `PTmmMssS`
  - Example: `PT18M14S`
  - _18 minutes, 14 seconds_
- _Exact date example_
  ```html
  <time datetime="1963-11-23T12:16:20Z">Premiere of the most important TV show of all time!</time>
  ```
- _Simple time period_
  ```html
  <time datetime="P365DT6H8M">Earth’s orbital period</time>
  ```
- _Range of time periods_

  ```html
  Opossum gestation period: <time datetime="P12D">twelve</time> to <time datetime="P13D">thirteen</time> days.
  ```

- [HTML indentation](https://learntheweb.courses/topics/html-indentation/)
- [Topics](https://learntheweb.courses/topics/#language/html-semantics-cheat-sheet)
- [HTML semantics checklist](https://learntheweb.courses/topics/html-semantics-checklist/)