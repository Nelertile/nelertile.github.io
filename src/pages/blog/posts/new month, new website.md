---
layout: ../../../layouts/MDPostLayout.astro
title: New Month, New Website?
author: Nelertile
description: "Discussing changes in my new website."
image:
  url: "/Nelertile_Logo.svg"
  alt: "Nelertile's Logo"
pubDate: 2023-02-26
tags: ["dev", "website", "monthly"]
---

Hello! This is my first monthly post, on my new blog!
<br>From here on out, I'll be making a post at the end of every month.

This month I have:

1. Practiced a lot of trumpet!
2. Gotten back in to Genshin Impact
3. Redone my website in [Astro](https://astro.build/)

Let's talk more about this new website.

The first major improvement I made was switching from [Vue](https://vuejs.org/) (which was only used for routing at the time) to [Astro](https://astro.build/), a much more robust system for websites like this!

I also made use of components for the Works page.

<p class="note">works.astro</p>

```astro
<div class="works-scroller snaps-inline">
    {
      Works.map((i) => (
        <Workscard title={i.title} href={i.href} img={i.img} />
      ))
    }
  </div>
```

<p class="note">Workscard.astro</p>

```astro
---
export interface Props {
  title: string;
  img: string;
  href: string;
}

const { href, title, img } = Astro.props;

const imgPath = `/works/img/${img}`;
---

<div class="works-element">
  <a href={href}>
    <img src={imgPath} alt="Project" />
    <h3>{title}</h3>
  </a>
</div>
```

With that being said, this was it for my first monthly post!
