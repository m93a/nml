# nml
Namespace Markup Language

## Work in progress!
This spec is not finished yet! For more info about nml, you can check out my [parser](https://github.com/m93a/nml-parser/).

## Intro

### What's nml?
The Namespace Markup Language (`nml`) is a try to create more powerful and user-friendly version of The Extensible Markup Language, aka. `xml`. It's name is a creation of [Phil Andy](https://github.com/philandy), originally thought to be a name of a community-maintaned version of `html` (see [this thread](https://github.com/OscarGodson/HTML6/issues/17#issuecomment-21987975) for more info).

### What's wrong with xml?
Are you a big fan of `xml`? Me too. "But - wait!" you say, "Then why are you trying to get rid of it?". I am not. `nml` will probably never replace `xml`. And it's not its goal. `nml` can be easily converted to `xml` at any time.
The problem with `xml` is that it's easy-to-read for parsers but hard-to-write for programmers. Why nobody uses `xhtml`? Because they would lose those comfortable features like boolean attributes, unquoted values and UPPERCASE TAG NAMES (yes, some people still use them). The goal of `nml` is to be as comfortable as possible without losing nothing of `xml` readability.

### What language is nml's default for defining namespaces?
Huh, that's a good point. Actually - I don't know. Personally I'd like to use something based on `css` syntax but there are many, many possibilities and it's better to let the community decide.

### Who is this spec for?
This spec is intended to be suitable for everybody, either a beginner or an expert writing his own nml-based browser-or-something. You will find four types of content here - normative sections for parser-makers, advanced sections for users that know `xml` and `html` and beginner sections for - wait for it... - beginners! The fourth type is an example for better understanding. Note that the advanced sections may be omitted on places without any difference from `xml` and `html`.

## The Spec Itself

### Document
**Beginner section**  
Basically, any file written in `nml` is a _document_. Document is set of everything in your file. The building unit of document are _tags_ and _text_.

**Example**
```html
<library>
 <book id=1 >The Little Prince</book>
 <book id=2 >The Universe Versus Alex Woods</book>
 <book id=42>The Hitchhikers Guide to The Galaxy</book>
</library>
```
**Normative section**
//TODO

### Tag
**Beginner section**
//TODO

**Advanced section**
//TODO  
Characters allowed in attribute and tag names (and rule):
 * all the characters
 * not a controll character (0 - 1F, 7F - 9F)
 * not a surrogate character (D800 - DFFF)
 * not a special character in range FFF0 - FFFB and FFFE - FFFF
 * not a whitespace character (20)

**Normative section**
//TODO
Tagname in regex: `[A-Za-z0-9](?[\N{U+0030}-\N{U+0039}\N{U+0040}-\N{U+007E}\N{U+00A1}-\N{U+D7FF}\N{U+E000}-\N{U+FFE9}\N{U+FFFC}\N{U+FFFD}])*(\s*:\s*<[A-Za-z0-9](?[\N{U+0021}-\N{U+0039}\N{U+0040}-\N{U+007E}\N{U+00A1}-\N{U+D7FF}\N{U+E000}-\N{U+FFE9}\N{U+FFFC}\N{U+FFFD}])*)?`

### //TODO

## Outro

### Credits
m93a (Michal Grňo) - The Writer (I wrote this spec)  
Oscar Godson - The Uniter (he brought us together)  
Phil Andy - The Name Creator (he created this cool name)  
W3C - Thanks for standardizing the Web and sorry for breaking your standards :)  

### External specs
 * [Regex, Perl extension](http://perldoc.perl.org/perlre.html#Regular-Expressions)

### License
Copyright (c) from 00:00:00 1970-01-01 to 03:14:07 2038-01-19 in Big-Endian by The Community.

OK, actually I (where `I` is a pointer to `m93a`) am the owner but just wanted to say you are free do anything with this spec until the End of Time.

All the software here is provided "[AS IS](http://en.wikipedia.org/wiki/As_is)", without warranty of any kind etc. You know what I mean.

And you probably shouldn't try to appropriate or something this spec, treat according to your conscience.
