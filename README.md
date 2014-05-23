Template CSS
============
Parses HTML template into SASS.

    <div class="well" style="margin:5px">
        <span class="title" style="font-size:2em"></span>
    </div>

or Jade

    div.well(margin:5px)
        span.title(font-size:2em)

turns into

    div.well {
        margin:5px
        span.title {
            font-size:5px
        }
    }

also support wildcard elements using tc namespace

    <div class="well" style="margin:5px">
        <tc:any class="title" style="font-size:2em"></tc:any>
    </div>
    ...
    div.well {
        margin:5px
        *.title {
            font-size:2em
        }
    }

and pseudo selectors

    <div:focus class="well" style="margin:5px">
        <tc:any class="title" style="font-size:2em"></tc:any>
    </div:focus>
    ...
    div:focus.well {
        margin:5px
        *.title {
            font-size:2em
        }
    }

with additional support for any other crazy shit you want to do

    <div class="well" style="margin:5px">
        <tc:any tc:selector=":not(:first-child)"></tc:any>
    </div>
    ...
    div.well {
        margin:5px
        *:not(:first-child) {
            font-size:2em
        }
    }