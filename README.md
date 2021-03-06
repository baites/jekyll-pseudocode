# jekyll-pseudocode
A pseudocode/algorithm formatter for sites powered by jekyll. This is a fork from wkm/jekyll-pseudo.

Sometimes you don't want to use a particular programming language to
demonstrate a concept because of the syntactic overhead. jekyll-pseudocode lets
you use a gently styled free-formated representation.

## Language
* indentation is preserved
* a word beginning with a capital letter is a keyword
* a word followed by parentheses is a function name
* all other words are variables
* words within double quotes are generally strings

* these symbols are auto-formatted: `<-- <= >= --> =`


Sample output:

    {% pseudo %}
    Function swap(old, new)
      remaining <- quorumSize
      success <- False
      For Each host
        result[host] <- send(host, propose(old, new))
        If result[host] = "ok"
          remaining--
      If remaining > 1+quorumSize/2
        success <- True
      For Each result
        If success
          send(host, confirm(old, new))
        Else
          send(host, cancel(old, new))
    {% endpseudo %}

## Output
Output is annotated with `<span>` classes and can be styled using CSS. Typically keywords are made bold and variables are italicized.

Using the style provided in `lib/jekyll-pseudocode.scss` previous markdown should be rendered as:

![Image](https://raw.github.com/baites/jekyll-pseudocode/master/doc/screenshot.png)

## Author
Victor Bazterra ([@baites](https://github.com/baites)) fork from jekyll-pseudo
project by Wiktor Macura ([@wkm](https://github.com/wkm)). I have done
only minimal changes in updating some grammar. I also provided with a scss with
the style I like.

I stop working in the project so no changes are expected from me.

## Acknowledgement
Thanks Tate Tian ([@tatetian](https://github.com/tatetian)) for the great
project.
