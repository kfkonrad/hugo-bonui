# Hugo bonUI Portfolio theme

![Hugo bonUI Portfolio](https://api.uicard.io/uploads/fbb72e1060675dc28fd8a6f02b0be9c4.jpg)

Hugo bonUI portfolio theme is designed especially for designers and developers who need a good-looking portfolio website without much effort.
It includes all the components to showcase the skills, work, projects and the like.

## How to configure

All content for the portfolio will be reside in `data/config.yml`.

You'll be providing at least two top-level elements: `header` and `sidebar`. `header` simply contains your Name for the title and sidebar will configure the content for the left-hand side of the portfolio.

`contents` defines the content of your portfolio and `contact` provides an email form. Both can be omitted, but my advise would be to utilize at least one of them for a not-so-empty website.

This is an example `config.yml`. You can find detailed descriptions of the complicated bits below.
```yaml
header:
  author: Jane Doe

contact:
  email: my@awesome-email.com
  message_on_success: 'You have mail!'

sidebar:
  title: welcome to my homepage, i'm
  highlightedtext: jane
  description: a developer based in germany
  displaypicture: portrait.jpg
  social:
    facebook:
      brand: https://facebook.com/<yourusername>
    github:
      brand: https://github.com/<yourusername>
    envelope:
      solid: mailto:<your@email.com>

contents:
  - type: progressbars
    title: Skills
    color: yellow
    entries:
      Photoshop: 50
      Python: 68
  - type: timeline
    title: Experience
    color: green
    entries:
      - company: My Great Employer
        jobtitle: Master of Desaster
        timeperiod: Aug 2012 - Jan 2015
        website: https://mygreatemployer.whatever
        description: |
          I did some great work
          with them, they are fine people
  - type: cards
    title: Projects
    color: orange
    entries:
      - title: Lorem
        icon:
          code: solid
        description: |
          Nunc sapien nisi, maximus eleifend hendrerit sit amet, rutrum vel
          diam. Duis quam nibh, tincidunt eget nunc nec, suscipit pretium dolor.
```

### `sidebar`

`sidebar` let's you define a few catching phrases, place a picture and display your social media accounts.

bonUI supports all free Font Awesome Icons in all four styles, but this needs a little data: First you provide the name of the icon, then the style and the hyperlink to link to. Depending on the icon the available styles may include `brand` (company/brand icons), `light`, `regular` and/or `bold`.

```yaml
sidebar:
  title: welcome to my homepage, i'm
  highlightedtext: jane
  description: a developer based in germany
  displaypicture: portrait.jpg
  social:
    facebook:
      brand: https://facebook.com/<yourusername>
    github:
      brand: https://github.com/<yourusername>
    envelope:
      solid: mailto:<your@email.com>
```

### `contents`
`contents` is a list of sections with three possilbe types: `progressbars`, `timeline` and `cards`.
They share the keys `type`, `color`, `title` and `entries`, with just `entries` being different for each type of content.

All types support choosing and customizing the backgroud color. The colors `red`, `blue`, `yellow`, `green`, `orange` and `purple` are predefined. See section customizing on how to (re)define colors.

#### `progressbars`

Progressbars can signal e.g. progress or level of skill in certain areas.

The key (e.g. Photoshop) will be printed above the bar. The value (e.g. 50) is an integer functioning as the percentage value of the progress bar.

```yaml
contents:
  - type: progressbars
    title: Skills
    color: yellow
    entries:
      Photoshop: 50
      Python: 68
```

#### `timeline`

Show projects or employers over time with a timeline.

Each entry consists of four key/value pairs: `title`, `subtitle`, `timeperiod` and `description` with `subtitle` and `description` being optional.

Please note that the subtitle is actually shown above the title, but in a smaller font. This is ideal for displaying details like your job title at the first glance.

```yaml
contents:
  - type: timeline
    title: Experience
    color: green
    entries:
      - title: My Great Employer
        subtitle: Master of Desaster
        timeperiod: Aug 2012 - Jan 2015
        website: https://mygreatemployer.whatever
        description: |
          I did some great work
          with them, they are fine people
```

#### `cards`

Showcase description of e.g. projects and favorite quotes with cards. `cards` are displayed in two columns and with a Font Awesome icon.

Simply define the title, the icon in the format `icon-name: icon-type` (optional) and give your card a `description`.

```yaml
contents:
  - type: cards
    title: Projects
    color: orange
    entries:
      - title: Lorem
        icon:
          code: solid
        description: |
          Nunc sapien nisi, maximus eleifend hendrerit sit amet, rutrum vel
          diam. Duis quam nibh, tincidunt eget nunc nec, suscipit pretium dolor.
```
