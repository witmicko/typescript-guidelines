## Whitespace

  - [18.1](#18.1) <a name='18.1'></a> Use soft tabs set to 2 spaces. eslint: [`indent`](http://eslint.org/docs/rules/indent.html) jscs: [`validateIndentation`](http://jscs.info/rule/validateIndentation)

    ```typescript
    // bad
    function foo() {
    ∙∙∙∙const name;
    }

    // bad
    function bar() {
    ∙const name;
    }

    // good
    function baz() {
    ∙∙const name;
    }
    ```

  - [18.2](#18.2) <a name='18.2'></a> Place 1 space before the leading brace. eslint: [`space-before-blocks`](http://eslint.org/docs/rules/space-before-blocks.html) jscs: [`requireSpaceBeforeBlockStatements`](http://jscs.info/rule/requireSpaceBeforeBlockStatements)

    ```typescript
    // bad
    function test(){
      console.log('test');
    }

    // good
    function test() {
      console.log('test');
    }

    // bad
    dog.set('attr',{
      age: '1 year',
      breed: 'Bernese Mountain Dog',
    });

    // good
    dog.set('attr', {
      age: '1 year',
      breed: 'Bernese Mountain Dog',
    });
    ```

  - [18.3](#18.3) <a name='18.3'></a> Place 1 space before the opening parenthesis in control statements (`if`, `while` etc.). Place no space between the argument list and the function name in function calls and declarations. eslint: [`space-after-keywords`](http://eslint.org/docs/rules/space-after-keywords.html), [`space-before-keywords`](http://eslint.org/docs/rules/space-before-keywords.html) jscs:  [`requireSpaceAfterKeywords`](http://jscs.info/rule/requireSpaceAfterKeywords)

    ```typescript
    // bad
    if(isJedi) {
      fight ();
    }

    // good
    if (isJedi) {
      fight();
    }

    // bad
    function fight () {
      console.log ('Swooosh!');
    }

    // good
    function fight() {
      console.log('Swooosh!');
    }
    ```

  - [18.4](#18.4) <a name='18.4'></a> Set off operators with spaces. eslint: [`space-infix-ops`](http://eslint.org/docs/rules/space-infix-ops.html) jscs: [`requireSpaceBeforeBinaryOperators`](http://jscs.info/rule/requireSpaceBeforeBinaryOperators), [`requireSpaceAfterBinaryOperators`](http://jscs.info/rule/requireSpaceAfterBinaryOperators)

    ```typescript
    // bad
    const x=y+5;

    // good
    const x = y + 5;
    ```

  - [18.5](#18.5) <a name='18.5'></a> End files with a single newline character.

    ```typescript
    // bad
    (function (global) {
      // ...stuff...
    })(this);
    ```

    ```typescript
    // bad
    (function (global) {
      // ...stuff...
    })(this);↵
    ↵
    ```

    ```typescript
    // good
    (function (global) {
      // ...stuff...
    })(this);↵
    ```

  - [18.6](#18.6) <a name='18.6'></a> Use indentation when making long method chains (more than 2 method chains). Use a leading dot, which
    emphasizes that the line is a method call, not a new statement. eslint: [`newline-per-chained-call`](http://eslint.org/docs/rules/newline-per-chained-call) [`no-whitespace-before-property`](http://eslint.org/docs/rules/no-whitespace-before-property)

    ```typescript
    // bad
    $('#items').find('.selected').highlight().end().find('.open').updateCount();

    // bad
    $('#items').
      find('.selected').
        highlight().
        end().
      find('.open').
        updateCount();

    // good
    $('#items')
      .find('.selected')
        .highlight()
        .end()
      .find('.open')
        .updateCount();

    // bad
    const leds = stage.selectAll('.led').data(data).enter().append('svg:svg').classed('led', true)
        .attr('width', (radius + margin) * 2).append('svg:g')
        .attr('transform', 'translate(' + (radius + margin) + ',' + (radius + margin) + ')')
        .call(tron.led);

    // good
    const leds = stage.selectAll('.led')
        .data(data)
      .enter().append('svg:svg')
        .classed('led', true)
        .attr('width', (radius + margin) * 2)
      .append('svg:g')
        .attr('transform', 'translate(' + (radius + margin) + ',' + (radius + margin) + ')')
        .call(tron.led);

    // good
    const leds = stage.selectAll('.led').data(data);
    ```

  - [18.7](#18.7) <a name='18.7'></a> Leave a blank line after blocks and before the next statement. jscs: [`requirePaddingNewLinesAfterBlocks`](http://jscs.info/rule/requirePaddingNewLinesAfterBlocks)

    ```typescript
    // bad
    if (foo) {
      return bar;
    }
    return baz;

    // good
    if (foo) {
      return bar;
    }

    return baz;

    // bad
    const obj = {
      foo() {
      },
      bar() {
      },
    };
    return obj;

    // good
    const obj = {
      foo() {
      },

      bar() {
      },
    };

    return obj;

    // bad
    const arr = [
      function foo() {
      },
      function bar() {
      },
    ];
    return arr;

    // good
    const arr = [
      function foo() {
      },

      function bar() {
      },
    ];

    return arr;
    ```

  - [18.8](#18.8) <a name='18.8'></a> Do not pad your blocks with blank lines. eslint: [`padded-blocks`](http://eslint.org/docs/rules/padded-blocks.html) jscs:  [`disallowPaddingNewlinesInBlocks`](http://jscs.info/rule/disallowPaddingNewlinesInBlocks)

    ```typescript
    // bad
    function bar() {

      console.log(foo);

    }

    // also bad
    if (baz) {

      console.log(qux);
    } else {
      console.log(foo);

    }

    // good
    function bar() {
      console.log(foo);
    }

    // good
    if (baz) {
      console.log(qux);
    } else {
      console.log(foo);
    }
    ```

  - [18.9](#18.9) <a name='18.9'></a> Do not add spaces inside parentheses. eslint: [`space-in-parens`](http://eslint.org/docs/rules/space-in-parens.html) jscs: [`disallowSpacesInsideParentheses`](http://jscs.info/rule/disallowSpacesInsideParentheses)

    ```typescript
    // bad
    function bar( foo ) {
      return foo;
    }

    // good
    function bar(foo) {
      return foo;
    }

    // bad
    if ( foo ) {
      console.log(foo);
    }

    // good
    if (foo) {
      console.log(foo);
    }
    ```

  - [18.10](#18.10) <a name='18.10'></a> Do not add spaces inside brackets. eslint: [`array-bracket-spacing`](http://eslint.org/docs/rules/array-bracket-spacing.html) jscs: [`disallowSpacesInsideArrayBrackets`](http://jscs.info/rule/disallowSpacesInsideArrayBrackets)

    ```typescript
    // bad
    const foo = [ 1, 2, 3 ];
    console.log(foo[ 0 ]);

    // good
    const foo = [1, 2, 3];
    console.log(foo[0]);
    ```

  - [18.11](#18.11) <a name='18.11'></a> Add spaces inside curly braces. eslint: [`object-curly-spacing`](http://eslint.org/docs/rules/object-curly-spacing.html) jscs: [`disallowSpacesInsideObjectBrackets`](http://jscs.info/rule/disallowSpacesInsideObjectBrackets)

    ```typescript
    // bad
    const foo = {clark: 'kent'};

    // good
    const foo = { clark: 'kent' };
    ```

  - [18.12](#18.12) <a name='18.12'></a> Avoid having lines of code that are longer than 100 characters (including whitespace). eslint: [`max-len`](http://eslint.org/docs/rules/max-len.html) jscs: [`maximumLineLength`](http://jscs.info/rule/maximumLineLength)

    > Why? This ensures readability and maintainability.

    ```typescript
    // bad
    const foo = 'Whatever national crop flips the window. The cartoon reverts within the screw. Whatever wizard constrains a helpful ally. The counterpart ascends!';

    // bad
    $.ajax({ method: 'POST', url: 'https://airbnb.com/', data: { name: 'John' } }).done(() => console.log('Congratulations!')).fail(() => console.log('You have failed this city.'));

    // good
    const foo = 'Whatever national crop flips the window. The cartoon reverts within the screw. ' +
      'Whatever wizard constrains a helpful ally. The counterpart ascends!';

    // good
    $.ajax({
      method: 'POST',
      url: 'https://airbnb.com/',
      data: { name: 'John' },
    })
      .done(() => console.log('Congratulations!'))
      .fail(() => console.log('You have failed this city.'));
    ```