---
description: Domponents and formatting examples used in pure-hugo.
title: Cards
toc_max: 3
grid:
- title: Option 1
  description: Option 1 description.
  icon: install_desktop
  link: /option1/
- title: Option 2
  description: Option 2 description.
  icon: developer_board
  link: /option2/
- title: Option 3
  description: Option 3 description.
  icon: build
  link: /option3/
---

Cards can be added to a page using the `card` shortcode.
The parameters for this shortcode are:

| Parameter   | Description                                                          |
| ----------- | -------------------------------------------------------------------- |
| title       | The title of the card                                                |
| icon        | The icon slug of the card                                            |
| image       | Use a custom image instead of an icon (mutually exclusive with icon) |
| link        | (Optional) The link target of the card, when clicked                 |
| description | A description text, in Markdown                                      |

> [!NOTE]
>
> There's a known limitation with the Markdown description of cards,
> in that they can't contain relative links, pointing to other .md documents.
> Such links won't render correctly. Instead, use an absolute link to the URL
> path of the page that you want to link to.
>
> For example, instead of linking to `../install/linux.md`, write:
> `/engine/install/linux/`.

## Example

{{< card
  title="Option 1"
  icon=favorite
  link=https://echjansen.com/
  description="Option 1 description" >}}

## Markup

```go
{{</* card
  title="Option 1"
  icon=favorite
  link=https://echjansen.com/
  description="Option 1 description"
*/>}}
```

### Grid

There's also a built-in `grid` shortcode that generates a grid of cards.
The grid size is 3x3 on large screens, 2x2 on medium, and single column on small.

{{< grid >}}

Grid is a separate shortcode from `card`, but it implements the same component under the hood.
The markup you use to insert a grid is slightly unconventional. The grid shortcode takes no arguments.
All it does is let you specify where on a page you want your grid to appear.

```go
{{</* grid */>}}
```

The data for the grid is defined in the front matter of the page, under the `grid` key, as follows:

```yaml
# front matter section of a page
title: some page
grid:
- title: Option 1
  description: Option 1 description.
  icon: install_desktop
  link: /option1/
- title: Option 2
  description: Option 2 description.
  icon: developer_board
  link: /option2/
- title: Option 3
  description: Option 3 description.
  icon: build
  link: /option3/
```
