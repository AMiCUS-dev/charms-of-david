# Day 1: Landing Page

Build a landing page with a centered search bar overlapping a campfire illustration.

![Landing Page Result](01-landing-page.png)

---

## Setup

The images you need are already in `app/static/`:

- `background-pattern.png`
- `campfire.png`

You'll reference them using `../static/filename.png` because your HTML file is in `templates/` and needs to go up one
level to reach `static/`.

[🤔 What does ../ mean in file paths?](https://claude.ai/new?q=I%27m%20learning%20web%20development.%20What%20does%20..%2F%20mean%20in%20a%20file%20path%3F%20Why%20would%20I%20use%20..%2Fstatic%2Fimage.png%20instead%20of%20just%20image.png%3F%20Explain%20simply.)

Create this file:

```
charms-of-david/
└── templates/
    └── index.html
```

> **Why index.html?** It's the standard name for homepage files. Web servers automatically serve `index.html` when
> someone visits your site's root URL.

---

## Step 1: Base HTML Structure

Create `templates/index.html`:

```html
<!DOCTYPE html>
<html lang="ro">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ProjectName - Găsește cântecul potrivit</title>

    <!-- TODO: 1. Add TailwindCSS Play CDN -->

    <!-- TODO: 2. Add custom colors orange-25 & orange-75 -->

    <!-- TODO: 3. Add Inter font from Google Fonts -->
</head>
<body>

</body>
</html>
```

Add TailwindCSS using the Play
CDN. [🤔 What is TailwindCSS?](https://claude.ai/new?q=I%27m%20building%20my%20first%20website.%20What%20is%20TailwindCSS%20and%20why%20would%20I%20use%20it%20instead%20of%20writing%20regular%20CSS%3F%20Explain%20simply%20for%20a%20beginner.)

Find the script tag at [TailwindCSS Play CDN](https://tailwindcss.com/docs/installation/play-cdn) and paste it in
`<head>`.

---

## Step 2: Add Custom Colors

Tailwind includes many colors: `orange-50`, `orange-100`, `orange-200`, up to
`orange-950`. [See all default colors](https://tailwindcss.com/docs/customizing-colors).

Our design needs two extra shades not included by default:

- `orange-25` (very light)
- `orange-75` (between 50 and 100)

Add this in `<head>` after the TailwindCSS script:

```html

<style type="text/tailwindcss">
    @theme {
        /* TODO: 1. Define --color-orange-25 -> oklch(99.4% 0.008 73.263) */
        /* TODO: 2. Define --color-orange-75 -> oklch(96.7% 0.029 74.022) */
    }
</style>
```

[🤔 How does this work?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20how%20do%20I%20add%20custom%20colors%20using%20%40theme%3F%20I%20need%20to%20add%20orange-25%20and%20orange-75.%20Show%20me%20the%20exact%20syntax%20for%20v4.)

We're using oklch() for colors instead of hex codes (#ff5500) or
rgb(). [🤔 Why oklch?](https://claude.ai/new?q=In%20web%20development%2C%20why%20is%20oklch%20better%20than%20hex%20codes%2C%20RGB%2C%20or%20HSL%20for%20defining%20colors%3F%20Explain%20briefly%20for%20a%20beginner.)

Once added, you can use them like any Tailwind color: `bg-orange-25`, `text-orange-75`, etc.

---

## Step 3: Add Font

Add Inter font below the color styles:

```html

<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
<style>
    body {
        font-family: 'Inter', sans-serif;
    }
</style>
```

This loads the font from Google and sets it as default for your page.

---

## Step 4: Body Layout

You need a gradient background (orange-75 fading to orange-25) with a pattern image overlay.

```html

<body class="...">
<!-- TODO: 1. Add linear gradient from orange-75 to orange-25 (top to bottom) -->
<!-- TODO: 2. Make body fill full screen height -->
<!-- TODO: 3. Use flex column layout -->

<!-- Background Pattern -->
<img src="../static/background-pattern.png" class="...">
<!-- TODO: 1. Fix position (stays when scrolling) -->
<!-- TODO: 2. Cover entire screen (inset-0) -->
<!-- TODO: 3. Cover with size-full (width and height 100%) -->
<!-- TODO: 4. Set 50% opacity -->
<!-- TODO: 5. Make image cover the container -->
</body>
```

**What you need:**

For `<body>`:

- Linear gradient
  background. [🤔 How do I make gradients in v4?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20how%20do%20I%20create%20a%20linear%20gradient%20background%20from%20top%20to%20bottom%3F%20I%20want%20to%20go%20from%20orange-75%20to%20orange-25.%20What%27s%20the%20exact%20v4%20class%20syntax%3F)
- Full screen
  height. [🤔 How do I make body full height?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20what%20class%20makes%20the%20body%20element%20fill%20the%20full%20screen%20height%3F%20Give%20me%20the%20exact%20class%20name.)
- Flex column
  layout. [🤔 What is flex column?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20I%20want%20to%20stack%20elements%20vertically%20inside%20the%20body.%20What%20classes%20do%20I%20need%20for%20flexbox%20column%20layout%3F%20Give%20exact%20v4%20class%20names.)

For the pattern image:

- Fixed
  positioning. [🤔 What does fixed positioning do?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20I%20want%20a%20background%20image%20to%20stay%20in%20place%20when%20I%20scroll.%20What%20class%20makes%20an%20element%20fixed%3F%20And%20how%20do%20I%20make%20it%20cover%20the%20entire%20screen%20with%20inset-0%3F%20Give%20exact%20v4%20classes.)
- Full size with
  `size-full` [🤔 What is size-full?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20what%20does%20the%20size-full%20class%20do%3F%20How%20is%20it%20different%20from%20w-full%20h-full%3F)
- 50%
  opacity. [🤔 How do I change opacity?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20what%20class%20sets%20an%20element%27s%20opacity%20to%2050%25%3F%20Give%20me%20the%20exact%20class%20name.)
- Cover
  container. [🤔 How do I make images fit?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20I%20have%20an%20image%20that%20needs%20to%20fill%20its%20container%20completely.%20What%20class%20makes%20an%20image%20cover%20its%20container%3F%20Give%20exact%20v4%20class.)

**Test:** Open in browser. You should see an orange gradient with a subtle pattern overlay.

---

## Step 5: Navigation Bar

The nav bar has two parts: site name on the left, button on the right.

```html

<nav class="w-full px-6 py-6 md:px-12 flex justify-between items-center">
    <div class="...">
        ProjectName
        <!-- TODO: 1. Make text large (xl or 2xl) -->
        <!-- TODO: 2. Make it bold -->
        <!-- TODO: 3. Make it black -->
    </div>

    <button class="...">
        Trimite un cântec
        <!-- TODO: 1. Orange background (orange-500) -->
        <!-- TODO: 2. White text -->
        <!-- TODO: 3. Add padding (try px-6 py-2) -->
        <!-- TODO: 4. Make fully rounded -->
        <!-- TODO: 5. Add medium font weight -->
        <!-- TODO: 6. Smaller text on mobile, normal on desktop (sm: and md: prefixes) -->
        <!-- TODO: 7. OPTIONAL: Add hover effect (hover:bg-orange-400) -->
    </button>
</nav>
```

**What you need:**

For the site name:

- Large
  text. [🤔 What text sizes exist?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20what%20class%20makes%20text%20xl%20or%202xl%20size%3F%20What%20other%20text%20sizes%20are%20available%3F%20List%20the%20exact%20v4%20class%20names.)
- Bold
  text. [🤔 How do I make text bold?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20what%20class%20makes%20text%20bold%3F%20Give%20me%20the%20exact%20v4%20class%20name.)
- Black
  color. [🤔 How do I color text?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20what%20class%20makes%20text%20black%3F%20Give%20exact%20v4%20class%20name.)

For the button:

- Orange
  background. [🤔 How do I color backgrounds?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20what%20class%20gives%20an%20element%20an%20orange%20background%3F%20I%20want%20orange-500.%20Give%20exact%20v4%20class.)
-

Padding. [🤔 How do I add padding?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20how%20do%20I%20add%20padding%20to%20a%20button%3F%20I%20want%20padding%20on%20left%2Fright%20and%20top%2Fbottom.%20Show%20me%20common%20v4%20padding%20classes.)

- Rounded
  corners. [🤔 How do I round corners?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20what%20class%20makes%20a%20button%20fully%20rounded%20%28pill%20shape%29%3F%20Give%20exact%20v4%20class.)
- Responsive text with
  breakpoints. [🤔 How do responsive breakpoints work?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20explain%20the%20sm%3A%2C%20md%3A%2C%20and%20lg%3A%20prefixes.%20How%20do%20I%20make%20text%20change%20size%20at%20different%20screen%20widths%3F%20Give%20exact%20v4%20examples.)
- Medium font
  weight. [🤔 What font weights exist?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20what%20class%20makes%20text%20medium%20weight%3F%20What%20other%20font%20weights%20are%20available%3F)
- OPTIONAL: Hover
  effect. [🤔 How do hover states work?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20how%20do%20I%20add%20a%20hover%20effect%20to%20change%20a%20button%27s%20background%20color%3F%20Show%20me%20an%20example%20with%20hover%3A%20prefix.)

---

## Step 6: Main Content Area

This section takes all remaining space and centers its content.

```html

<main class="...">
    <!-- TODO: 1. Take remaining vertical space -->
    <!-- TODO: 2. Use flex column layout -->
    <!-- TODO: 3. Center content horizontally and vertically -->
    <!-- TODO: 4. Add responsive padding (try px-3, sm:px-4) -->
    <!-- TODO: 5. Add top margin on mobile only (mt-8 md:mt-0) -->

    <!-- Page title and search will go here -->
</main>
```

**What you need:**

- Grow to fill
  space. [🤔 How do I make an element fill remaining space?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20I%20have%20a%20flex%20container%20with%20a%20navigation%20bar%20and%20a%20main%20section.%20What%20class%20makes%20the%20main%20section%20take%20all%20remaining%20space%3F%20Give%20exact%20v4%20class.)
- Center
  content. [🤔 How do I center content?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20I%20want%20to%20center%20content%20both%20horizontally%20and%20vertically%20inside%20a%20flex%20container.%20What%20classes%20do%20I%20need%3F%20Give%20exact%20v4%20classes.)
- Responsive
  spacing. [🤔 How do I make spacing responsive?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20how%20do%20I%20add%20padding%20that%20changes%20at%20sm%3A%20and%20md%3A%20breakpoints%3F%20And%20how%20do%20I%20add%20top%20margin%20only%20on%20mobile%3F%20Give%20exact%20v4%20classes.)

---

## Step 7: Page Title

Add this as the first element inside `<main>`:

```html
<h1 class="...">
    Găsește cântecul potrivit.
</h1>
<!-- TODO: 1. Large text (3xl on mobile, 4xl on sm:, 5xl on md:) -->
<!-- TODO: 2. Make it bold -->
<!-- TODO: 3. Dark neutral color (neutral-900) -->
<!-- TODO: 4. Center the text -->
<!-- TODO: 5. Tighten letter spacing slightly -->
```

**What you need:**

- Responsive font
  sizes. [🤔 How do I change font size by screen size?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20how%20do%20I%20make%20a%20heading%20text-3xl%20on%20mobile%2C%20text-4xl%20on%20sm%3A%2C%20and%20text-5xl%20on%20md%3A%3F%20Give%20exact%20v4%20classes.)
- Center
  text. [🤔 How do I center text?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20what%20class%20centers%20text%20horizontally%3F%20Give%20exact%20v4%20class.)
- Letter
  spacing. [🤔 How do I adjust letter spacing?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20what%20class%20makes%20letters%20slightly%20closer%20together%20for%20a%20tighter%20look%3F%20Give%20exact%20v4%20class.)
- Neutral
  colors. [🤔 What are neutral colors?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20what%27s%20the%20difference%20between%20gray-900%20and%20neutral-900%3F%20When%20should%20I%20use%20each%3F)

---

## Step 8: Image + Search Container

The search bar will overlap the campfire image using layers and negative margin.

```
[Campfire Image] ← layer 10 (behind)
[Search Bar]     ← layer 20 (in front), pulled UP
```

Add this after the heading inside `<main>`:

```html

<div class="relative flex flex-col items-center w-full max-w-4xl">

    <!-- Campfire Image -->
    <div class="relative z-10 w-full flex justify-center">
        <img src="../static/campfire.png"
             alt="Campfire illustration"
             class="...">
        <!-- TODO: 1. Keep aspect ratio (object-contain) -->
        <!-- TODO: 2. Make width responsive (try md:w-3xl) -->
    </div>

    <!-- Search Bar Container -->
    <div class="...">
        <!-- TODO: 1. Position relative -->
        <!-- TODO: 2. Higher layer (z-20) -->
        <!-- TODO: 3. Full width -->
        <!-- TODO: 4. Max width 2xl -->
        <!-- TODO: 5. Pull up with negative margin (-mt-12 sm:-mt-16 lg:-mt-20) -->

        <!-- Search bar goes here (next step) -->
    </div>

</div>
```

**What you need:**

For the campfire image:

- Keep
  proportions. [🤔 How do I keep image aspect ratio?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20I%20want%20an%20image%20to%20keep%20its%20original%20proportions%20when%20resizing.%20What%27s%20the%20difference%20between%20object-contain%20and%20object-cover%3F%20Give%20exact%20v4%20class.)
- Responsive
  width. [🤔 How do I make image width responsive?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20how%20do%20I%20make%20an%20image%20have%20no%20width%20limit%20on%20mobile%20but%20a%20specific%20max-width%20on%20desktop%20using%20md%3Aw-3xl%3F)

For the search container:

- Control
  layers. [🤔 What is z-index?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20I%20want%20one%20element%20to%20appear%20on%20top%20of%20another.%20What%20is%20z-index%20and%20how%20do%20I%20use%20it%3F%20Show%20me%20z-10%20and%20z-20%20classes%20in%20v4.)
- Max
  width. [🤔 How do I limit element width?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20what%20class%20limits%20an%20element%27s%20maximum%20width%20to%202xl%3F%20Give%20exact%20v4%20class.)
- Negative
  margin. [🤔 How does negative margin work?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20I%20want%20to%20pull%20an%20element%20UP%20so%20it%20overlaps%20the%20element%20above%20it.%20Explain%20negative%20margin%20and%20show%20me%20how%20to%20use%20-mt-12%2C%20sm%3A-mt-16%2C%20lg%3A-mt-20%20in%20v4.)

---

## Step 9: Search Bar

Build a white rounded search bar with an input and button. This goes inside the search container from Step 8.

```html

<div class="...">
    <!-- TODO: 1. White background -->
    <!-- TODO: 2. Fully rounded -->
    <!-- TODO: 3. Subtle shadow (try shadow-xs) -->
    <!-- TODO: 4. Responsive padding (pl-3 sm:pl-4 for left, pe-1.5 sm:pe-2 for right, py-1.5 sm:py-2 for vertical) -->
    <!-- TODO: 5. Flex with items centered -->
    <!-- TODO: 6. Space between items -->
    <!-- TODO: 7. Subtle border (border border-neutral-100) -->

    <input type="text"
           placeholder="Caută după nume sau artist..."
           class="...">
    <!-- TODO: 1. Take all available space -->
    <!-- TODO: 2. Transparent background -->
    <!-- TODO: 3. Remove outline on focus -->
    <!-- TODO: 4. Neutral text color (neutral-700) -->
    <!-- TODO: 5. Neutral placeholder (neutral-500) -->
    <!-- TODO: 6. Add horizontal padding (px-4) -->
    <!-- TODO: 7. Responsive text size (text-lg sm:text-xl) -->

    <button class="...">
        <!-- TODO: 1. Orange background (orange-500) -->
        <!-- TODO: 2. White text -->
        <!-- TODO: 3. Fixed square size (h-12 w-12) -->
        <!-- TODO: 4. Fully rounded -->
        <!-- TODO: 5. Flex with centered items -->
        <!-- TODO: 6. Subtle shadow (shadow-xs) -->
        <!-- TODO: 7. OPTIONAL: Add hover effect and transition -->

        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24"
             stroke-width="2.5" stroke="currentColor" class="w-6 h-6">
            <path stroke-linecap="round" stroke-linejoin="round"
                  d="M21 21l-5.197-5.197m0 0A7.5 7.5 0 105.196 5.196a7.5 7.5 0 0010.607 10.607z"/>
        </svg>
    </button>
</div>
```

**What you need:**

For the container:

- Add
  shadow. [🤔 How do I add shadows?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20what%20are%20the%20different%20shadow%20classes%3F%20What%27s%20the%20difference%20between%20shadow-xs%2C%20shadow-sm%2C%20and%20shadow-lg%3F)
- Add
  border. [🤔 How do I add borders?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20how%20do%20I%20add%20a%20subtle%20border%20with%20neutral-100%20color%3F%20Give%20exact%20v4%20classes.)
- Space
  elements. [🤔 How do I space flex items?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20I%20have%20a%20flex%20container%20with%20an%20input%20and%20button.%20What%20class%20puts%20space%20between%20them%3F%20Give%20exact%20v4%20class.)
- Responsive padding with logical
  properties. [🤔 What is pl- and pe-?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20what%27s%20the%20difference%20between%20pl-%2C%20pr-%2C%20ps-%2C%20and%20pe-%20for%20padding%3F%20Why%20use%20logical%20properties%3F)

For the input:

- Take available
  space. [🤔 How do I make input fill space?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20I%20have%20a%20flex%20container%20with%20an%20input%20and%20a%20button.%20What%20class%20makes%20the%20input%20take%20all%20available%20space%3F%20Give%20exact%20v4%20class.)
- Remove focus
  outline. [🤔 How do I remove input outline?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20when%20I%20click%20an%20input%20field%2C%20it%20gets%20a%20blue%20outline.%20What%20class%20removes%20it%3F%20Give%20exact%20v4%20class.)
- Style
  placeholder. [🤔 How do I style placeholders?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20how%20do%20I%20make%20the%20placeholder%20text%20in%20an%20input%20field%20neutral-500%20color%3F%20Give%20exact%20v4%20class.)

For the button:

- Fixed
  size. [🤔 How do I set fixed width and height?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20I%20want%20a%20button%20to%20be%20exactly%2012%20units%20wide%20and%2012%20units%20tall%20%28a%20square%29.%20What%20classes%20do%20I%20use%3F%20Give%20exact%20v4%20classes.)
- Center
  icon. [🤔 How do I center button content?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20I%20have%20an%20icon%20inside%20a%20button.%20What%20classes%20center%20the%20icon%20perfectly%20in%20the%20middle%3F%20Give%20exact%20v4%20classes.)
- OPTIONAL: Transitions and
  hover. [🤔 How do I add smooth transitions?](https://claude.ai/new?q=In%20TailwindCSS%20v4%2C%20how%20do%20I%20add%20smooth%20transitions%20when%20hovering%20over%20a%20button%3F%20Show%20me%20transition%20classes%20and%20hover%20effects.)

---

## Test Your Work

Open `index.html` in browser. Resize the window from mobile to desktop.

Check:

- ✓ Gradient background with pattern
- ✓ Navigation with logo and button
- ✓ Centered title
- ✓ Search bar overlapping campfire
- ✓ Everything responds smoothly at different screen sizes (especially at small, medium, and large breakpoints)

Everything looks good? You're done! 🎉

**Stuck?** Ask Claude: "I'm trying to [what you want] but [what's happening]. Here's my code: [paste code]"