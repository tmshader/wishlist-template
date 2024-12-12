# Wishlist

An easy to configure website to host your christmas wistlist, styled exactly like those ugly christmas sweaters!

You can view an example here: [https://tmshader.me/wishlist-template/](https://tmshader.me/wishlist-template/)

## How to use

The page is build with Github Actions so you don't have to worry about that.

1. The first thing to take a look at is `_config.yml` where you can configure your website domain, the snow effect and whether you'd like to track the website traffic with Umami.

2. Next you have to edit `index.md` which contains your wishlist!

    You only need to edit between the `---` characters.

    You can first edit the title, the language, the button text and the image description text.

3. Now comes the good part!

    To add your wishes to the list you have to follow the following style:

    ```yaml
    wishlist:
        # This is the title of your wish
      - title: Blue Chocolate

        # This it the price of your wish without any currencies (for sorting and filtering)
        price: 1

        # This it the price of your wish as you'd like it to be displayed
        price_text: $1

        # This it the description of your wish
        description: Blue as the sky

        # Here you can add some tags to your wish
        tags: [round, chocolate]

        # And maybe a link where it can be bought
        link: https://en.wikipedia.org/wiki/Blue

        # A nice image to show what it is
        image: /assets/images/blue.png

        # And finally you can mark it as a favourite wish
        favourite: true
    ```

4. Now you can define categories to sort your wishes!

    ```yaml
    categories:
        # This is the title of the category
      - name: "My favourites"

        # And this is the type of the category
        type: "favourite"

        # And an id to make linking possible
        id: my-favourites

        # After this you can place the type-specific arguments, for example:
        over: 0
        under: 2
        tag: "chocolate"
    ```

5. Now you have to define your category types and how they filter!

    ```yaml
    category_headers:

      # This is what we put in "type" in the categories section
      favourite:

        # Add an id to make linking to the category header possible
        id: favourites

        # Set the text for the title
        header: Favourites

        # Define the filter for the category
        # Here are a few examples:
        filter: "wish.favourite == true"
        filter: "wish.price < category.under and wish.price >= category.over"
        filter: "wish.tags contains category.tag"
    ```

6. Aaaand you're done!

    Go and share the page with your friends and family so they know what to get you this christmas!



## Help! Something is not working!

Do not worry, just open an issue and I'll help you as soon as possible! :)



## License

The code is licensed under the [MIT License](LICENSE).