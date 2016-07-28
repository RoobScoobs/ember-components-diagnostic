# Ember Components Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  Give an example of a visual hierarchy that could be modeled with components.

    ```md
    To-do list
    ```

1.  What is the command to generate a new component called '`my-map`'?

    ```sh
    ember generate component my-map
    ```

1.  What files are edited to produce a component, and what are their
    responsibilities?

    ```md
    To define a component, create a template whose name starts with components/.
    The template is where the component is backed by an element, and in order to
    configure that component's behavior or actions you can edit the component file.
    ```

1.  Suppose you have a component '`my-contact`', which is loaded from
    '`app/contacts/template.hbs`' when visiting the `/contacts` path. What is
    the syntax for loading this component inside that template?

    ```html
    This is the syntax for the handlebars template loaded for contacts, which would
    send the data (of each contact) down to the component 'my-contact' to use.

    {{#each model as |contact|}}
      {{my-contact contact=contact}}
    {{/each}}
    ```

    Each contact has multiple phone numbers. Suppose you also have '`my-phone`'
    nested under '`my-contact`'. What is the code you would write in
    '`app/components/my-contact/template.hbs`' to load the nested component and
    pass it data?

    ```html
    This would be accessible through:
    app/contact/template.hbs
    {{my-contact contact=model}}

    which would send it down to:
    app/components/my-contact/template.hbs
    {{#each contact.numbers as |number|}}
      {{contact/number number=number}}
    {{/each}}
    ```
