# nml
Namespace Markup Language

## Work in progress!
This spec is not finished yet! For more info about nml, you can check out my [parser](https://github.com/m93a/nml-parser/).

## Intro

### What's nml?
The Namespace Markup Language (`nml`) is a try to create more powerful and user-friendly version of The Extensible Markup Language, aka. `xml`. It's name is a creation of [Phil Andy](https://github.com/philandy), originally thought to be a name of a community-maintaned version of `html` (see [this thread](https://github.com/OscarGodson/HTML6/issues/17#issuecomment-21987975) for more info).

### What's wrong with xml?
Are you a big fan of `xml`? Me too. "But - wait!" you say, "Then why are you trying to get rid of it?". I am not. `nml` will probably never replace `xml`. And it's not its goal. `nml` can be easily converted to `xml` at any time.
The problem with `xml` is that it's easy-to-read for parsers but hard-to-write for programmers. Why nobody uses `xhtml`? Because they would lose those comfortable features like boolean attributes, unquoted values and UPPERCASE TAG NAMES (yes, some people still use them). The goal of `nml` is to be as comfortable as possible without losing `xml`'s readability.

### What language is nml's default for defining namespaces?
Huh, that's a good point. Actually - I don't know. Personally I'd like to use something based on `css` syntax but there are many, many possibilities and it's better let the community decide.

### Who is this spec for?
This spec is intended to be suitable for everybody, either a beginner or an expert writing his own nml-based browser-or-something. You will find four types of content here - normative sections for parser-makers, advanced sections for users that know `xml` and `html` and beginner sections for - wait for it... - beginners! The fourth type is an example section for better understanding. Note that the advanced sections may be omitted on places without any difference from `xml` and `html`.

## The Spec Itself

### Document
**Beginner section**  
Basically, any file written in `nml` is a _document_. Document is a set of everything in your file. The building units of a document are _tags_ and _text_.

**Example**
```html
<library>
 <book id=1 >The Little Prince</book>
 <book id=2 >The Universe Versus Alex Woods</book>
 <book id=42>The Hitchhikers Guide to The Galaxy</book>
</library>
```

### Tag
**Beginner section**  
Tags are used to structure the document. Tags is the things between `<` and `>` characters.  
There are three types of tags:
 * Single tag
 * Begin tag
 * End tag

Begin tag looks like this: `<name>`. They mark the beginning of the `name` _element_.  
End tag is similar to begin tag but it has a slash at the beginning: `</name>`. It marks the end of the `name` _element_.  
Single tag is a combination of begin and end tags. It looks like this: `<name />` and means the same as this: `<name></name>`, it creates an _empty element_.

What does _element_ mean? Elements are virtual parts of the document that have a special meaning. Elements may have child elements but they don't have to. As a example of what they can do: in `html api` there's a `a` element used to mark that this piece of text is a anchor/link.

Single and begin tags may have _attributes_ to keep some information. They're based on a simple `foo=bar` format, written
right after the element name (and a space). In this examle, `foo` is called _attribute name_ or _key_ and `bar` is an
_attribute value_. If you want to use whitespace characters in value, you have to quote it this way: `foo="some bars"`.

There are also _single attributes_ (also called _boolean_), created by omitting the value and equal sign. Eg. attribute `bool` means `bool=""` (value is empty).

**Example**  
`<abc>` - Begin tag of an `abc` element.  
`</foobar>` - End tag of a `foobar` element.  
`<name first=Joe middle=Patata last=Rodriguez />` - Single tag of a `name` element with three attributes.  
`<a>Hi there!</a>` - A text between two tags, making one `a` element together.  
`<x><foo /></x>` - The `foo` element is a child of the `x` element.  
`<hello world />` - Element `hello` with a single attribute `world`.  
`<warning catch=attribute/>` - **Begin tag** (!) - that's because the slash is a part of attribute value.  
`<warning catch=attribute />` - Single tag, attribute value and the slash are divided by a space.  

**Advanced section**  
Single elements are interpreted the same way as in xml.  
Attributes are interpreted the same way in html5 (unquoted and single attributes are allowed).

All characters in following range are allowed in tag and attribute names: `U+0041` (LATIN CAPITAL LETTER A) to `U+02AF` (LATIN SMALL LETTER TURNED H WITH FISHHOOK AND TAIL).

**Normative section**  
//TODO  
Tagname (regex): `[A-\u02AF#$@_]*`

### //TODO

## Outro

### Credits
[m93a](http://m93a.g6.cz) (Michal Grňo) - wrote this spec  
[Oscar Godson](http://oscargodson.com) - invented the way to blend html & xml syntax  
[Phil Andy](https://github.com/philandy) - created the name  
W3C - Thanks for standardizing the Web and sorry for breaking your standards :)  

### External specs
 * [Regex, Perl extension](http://perldoc.perl.org/perlre.html#Regular-Expressions)

### License
Copyright (c) 2015 Michal Grňo

Permission is hereby granted, free of charge, to any person
obtaining a copy of this software and associated documentation
files (the "Software"), to deal in the Software without
restriction, including without limitation the rights to use,
copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the
Software is furnished to do so, subject to the following
conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES
OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT
HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY,
WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR
OTHER DEALINGS IN THE SOFTWARE.
