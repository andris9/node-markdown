node-markdown
=============

**node-markdown** is based on [Showdown](http://attacklab.net/showdown/) parser and is meant to parse [Markdown](http://daringfireball.net/projects/markdown/) syntax into HTML code.

Installation
------------

Use `npm` package manager

    npm install node-markdown


Usage
-----

Include Markdown parser

    var md = require("node-markdown").Markdown;

Parse Markdown syntax into HTML

    var html = md("**markdown** string");

Complete example

    var md_text = "**bold** *italic* [link](http://www.neti.ee) `code block`",
        md_parser = require("node-markdown").Markdown;

    // simple
    console.log(md_parser(md_text));
    
    // limit HTML tags and attributes
    console.log(md_parser(md_text, true, 'h1|p|span'));
    
    // limit HTML tags and keep attributes for allowed tags
    var allowedTags = 'a|img';
        allowedAttributes = {
            'a':'href|style',
            'img': 'src',
            '*': 'title'
        }
    console.log(md_parser(md_text, true, allowedTags, allowedAttributes));
