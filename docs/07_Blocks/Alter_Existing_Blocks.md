## Alter a block's build

Here are a few examples of how to alter the builds for any block:

```
/**
 * Implements hook_blocks_build_alter().
 */
function my_module_blocks_build_alter(blocks) {

  // Move the logo block to the footer region for authenticated users.
  if (dg.currentUser().isAuthenticated()) {
    blocks.logo._region = 'footer';
  }

  // Add some content before and after the main menu block.
  blocks.main_menu._prefix = '<p>$19.95 + shipping</p>';
  blocks.main_menu._suffix = dg.render({
    _theme: 'item_list',
    _items: ['Foo', 'Bar']
  });

}
```

## Alter a blocks's view

Here are a few examples of how to alter the view (i.e. block content) for any block:

```
/**
 * Implements hook_block_view_alter().
 */
function my_module_block_view_alter(element, block) {

  // Inspect the element and block to reveal who and what to alter.
  //console.log(block.get('id'), element, block);

  switch (block.get('id')) {

    // Add a link to the main menu.
    case 'main_menu':
      element.menu._items.push(
        dg.l('Map', 'map')
      );
      break;

    // Make the powered by block's text red and add a custom class to it.
    case 'powered_by':
      element.list._attributes.style = 'color: red;';
      element.list._attributes['class'].push('foo');
      break;

  }
  
  // On the hello world page, add a prefix to the title block.
  if (dg.router.getRouteKey() == 'example.hello-world' && block.get('id') == 'title') {
    element._prefix = '<i class="fa fa-cog"></i>';
  }

}
```
