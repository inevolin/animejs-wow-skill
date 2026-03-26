---
name: animejs-wow-skill
description: |
  Comprehensive skill for Anime.js v4 - a fast and flexible JavaScript animation library. 
  This skill should be used when implementing web animations, creating timelines, working with 
  SVG animations, scroll-based animations, draggable elements, staggered effects, immersive
  motion-first websites, or any JavaScript-based animation on the web. Triggers on: "anime.js",
  "animejs", "animate elements", "CSS animation with JS", "timeline animation",
  "stagger animation", "SVG morphing", "motion path", "scroll animation", "draggable",
  "spring animation", "keyframe animation", "animated landing page", "motion-first website",
  "Awwwards-style animation", "premium web UX", "interactive marketing site".
metadata:
  author: Ilja Nevolin
  repository: https://github.com/inevolin/animejs-wow-skill
---

# Anime.js WOW Skill

Anime.js is a lightweight JavaScript animation library with a simple yet powerful API. It works with CSS properties, SVG, DOM attributes, and JavaScript Objects.

## Installation

### NPM
```bash
npm install animejs
```

### ES Modules Import
```javascript
import { animate } from 'animejs';
```

### CDN (ES Modules)
```javascript
import { animate } from 'https://esm.sh/animejs';
```

### CDN (UMD)
```html
<script src="https://cdn.jsdelivr.net/npm/animejs/dist/bundles/anime.umd.min.js"></script>
<script>
  const { animate } = anime;
</script>
```

## Core Concepts

Anime.js v4 is modular and tree-shakeable. Import only what you need:

```javascript
// Full import
import { animate, createTimeline, stagger, createDraggable } from 'animejs';

// Standalone modules for smaller bundles
import { animate } from 'animejs/animation';
import { createTimeline } from 'animejs/timeline';
import { createTimer } from 'animejs/timer';
```

## Documentation Sitemap

The complete anime.js v4 documentation structure:

### Getting Started
- Installation (NPM, CDN, Direct download)
- Module imports (ES Modules, CommonJS, UMD)
- Using with vanilla JS
- Using with React

### Timer (`createTimer`)
- **Playback Settings**: delay, duration, loop, loopDelay, alternate, reversed, autoplay, frameRate, playbackRate
- **Callbacks**: onBegin, onComplete, onUpdate, onLoop, onPause, then()
- **Methods**: play(), reverse(), pause(), restart(), alternate(), resume(), complete(), reset(), cancel(), revert(), seek(), stretch()
- **Properties**: currentTime, progress, paused, completed, etc.

### Animation (`animate`)
- **Targets**: CSS Selector, DOM Elements, JavaScript Objects, Array of targets
- **Animatable Properties**: CSS Properties, CSS transforms, CSS Variables, JS Object properties, HTML Attributes, SVG Attributes
- **Tween Value Types**: Numerical, Unit conversion, Relative (+=, -=, *=), Color, Color function, CSS variable, Function based
- **Tween Parameters**: to, from, delay, duration, ease, composition, modifier
- **Keyframes**: Tween values, Tween parameters, Duration based, Percentage based
- **Playback Settings**: delay, duration, loop, loopDelay, alternate, reversed, autoplay, frameRate, playbackRate, playbackEase, persist
- **Callbacks**: onBegin, onComplete, onBeforeUpdate, onUpdate, onRender, onLoop, onPause, then()
- **Methods**: play(), reverse(), pause(), restart(), alternate(), resume(), complete(), cancel(), revert(), reset(), seek(), stretch(), refresh()

### Timeline (`createTimeline`)
- Add timers, Add animations, Sync WAAPI animations, Sync timelines, Call functions
- **Time Position**: Absolute (ms), Relative (<, >, +=, -=), Labels
- **Playback Settings**: defaults, delay, loop, loopDelay, alternate, reversed, autoplay, frameRate, playbackRate, playbackEase
- **Callbacks**: onBegin, onComplete, onBeforeUpdate, onUpdate, onRender, onLoop, onPause, then()
- **Methods**: add(), set(), sync(), label(), remove(), call(), init(), play(), reset(), reverse(), pause(), restart(), alternate(), resume(), complete(), cancel(), revert(), seek(), stretch(), refresh()

### Animatable (`createAnimatable`)
- **Settings**: unit, duration, ease, modifier
- **Methods**: Getters, Setters, revert()

### Draggable (`createDraggable`)
- **Axes Parameters**: x, y, snap, modifier, mapTo
- **Settings**: trigger, container, containerPadding, containerFriction, releaseContainerFriction, releaseMass, releaseStiffness, releaseDamping, velocityMultiplier, minVelocity, maxVelocity, releaseEase, dragSpeed, dragThreshold, scrollThreshold, scrollSpeed, cursor
- **Callbacks**: onGrab, onDrag, onUpdate, onRelease, onSnap, onSettle, onResize, onAfterResize
- **Methods**: disable(), enable(), setX(), setY(), animateInView(), scrollInView(), stop(), reset(), revert(), refresh()

### Layout (`createLayout`) - NEW
- **Usage**: Specifying a root, CSS display animation, Staggered layout, DOM order animation, Enter/Exit layout animation, Swap parent animation, Modal dialog animation
- **Settings**: children, delay, duration, ease, properties
- **States**: enterFrom, leaveTo, swapAt
- **Methods**: record(), animate(), update(), revert()
- Layout id attribute, Callbacks, Properties, Common gotchas

### Scope (`createScope`)
- Add constructor function, Register method function
- **Parameters**: root, defaults, mediaQueries
- **Methods**: add(), addOnce(), keepTime(), revert(), refresh()

### Events / Scroll (`onScroll`)
- **Settings**: container, target, debug, axis, repeat
- **Thresholds**: Numeric values, Positions shorthands, Relative position values, Min max
- **Synchronisation Modes**: Method names, Playback progress, Smooth scroll, Eased scroll
- **Callbacks**: onEnter, onEnterForward, onEnterBackward, onLeave, onLeaveForward, onLeaveBackward, onUpdate, onSyncComplete, onResize
- **Methods**: link(), refresh(), revert()

### SVG Utilities
- `morphTo()` - SVG shape morphing
- `createDrawable()` - SVG line drawing animation
- `createMotionPath()` - Motion path animation

### Text Utilities (`splitText`)
- **Settings**: lines, words, chars, debug, includeSpaces, accessible
- **Split Parameters**: class, wrap, clone
- HTML template support
- **Methods**: addEffect(), revert(), refresh()

### Utilities
- `stagger()` - Time/values/timeline staggering with grid support
- `$()` - Query selector utility
- `get()` / `set()` - Get/set CSS property values
- `cleanInlineStyles()` - Remove inline styles
- `remove()` - Remove animations from targets
- `sync()` - Synchronize animations
- `keepTime()` - Time keeper utility
- `random()` / `createSeededRandom()` / `randomPick()` / `shuffle()` - Random utilities
- `round()` / `clamp()` / `snap()` / `wrap()` - Math utilities
- `mapRange()` / `lerp()` / `damp()` - Interpolation utilities
- `roundPad()` / `padStart()` / `padEnd()` - String padding
- `degToRad()` / `radToDeg()` - Angle conversion
- Chain-able utilities

### Easings
- **Built-in**: linear, easeIn, easeOut, easeInOut (with Quad, Cubic, Quart, Quint, Sine, Expo, Circ, Back, Elastic, Bounce variants)
- **Custom**: Cubic Bezier, Linear (multi-point), Steps, Irregular
- **Spring**: `createSpring({ stiffness, damping, mass, velocity })`

### WAAPI (Web Animation API)
- When to use WAAPI vs JS animation
- Hardware-accelerated animations
- Improvements to native WAAPI
- API differences (iterations, direction, easing, finished)
- `waapi.convertEase()`

### Engine Configuration
- **Parameters**: timeUnit (ms/s), speed, fps, precision, pauseOnDocumentHidden
- **Methods**: update(), pause(), resume()
- Engine defaults

## Quick Reference

### Basic Animation
```javascript
import { animate } from 'animejs';

animate('.element', {
  translateX: 250,
  rotate: '1turn',
  duration: 800,
  ease: 'outExpo'
});
```

### Timeline
```javascript
import { createTimeline } from 'animejs';

const tl = createTimeline({ defaults: { duration: 500 } });
tl.add('.box1', { x: 100 })
  .add('.box2', { x: 100 }, '<')  // Start with previous
  .add('.box3', { x: 100 }, '-=200');  // 200ms before end
```

### Stagger
```javascript
import { animate, stagger } from 'animejs';

animate('.item', {
  translateY: [-20, 0],
  opacity: [0, 1],
  delay: stagger(100, { from: 'center' }),
  duration: 600
});
```

### Scroll Animation
```javascript
import { animate, onScroll } from 'animejs';

animate('.element', {
  translateX: [0, 500],
  autoplay: onScroll({
    target: '.element',
    sync: true
  })
});
```

### SVG Line Drawing
```javascript
import { animate, createDrawable } from 'animejs';

animate(createDrawable('path'), {
  draw: ['0 0', '0 1'],
  duration: 2000,
  ease: 'inOutQuad'
});
```

### Draggable
```javascript
import { createDraggable, createSpring } from 'animejs';

createDraggable('.draggable', {
  container: '.container',
  releaseEase: createSpring({ stiffness: 200, damping: 20 })
});
```

### Function-Based Values
```javascript
import { animate, random } from 'animejs';

animate('.element', {
  translateX: (el, i, total) => i * 50,
  rotate: () => random(-180, 180),
  delay: (el, i) => i * 100
});
```

### Keyframes
```javascript
animate('.element', {
  translateX: [
    { to: 100, duration: 500 },
    { to: 0, duration: 500, delay: 200 }
  ],
  rotate: ['0turn', '1turn', '0turn']
});
```

## React Integration

```jsx
import { useRef, useEffect } from 'react';
import { animate, createScope } from 'animejs';

function AnimatedComponent() {
  const root = useRef(null);
  const scope = useRef(null);

  useEffect(() => {
    scope.current = createScope({ root: root.current }).add(() => {
      animate('.box', { rotate: 360 });
    });
    return () => scope.current.revert();
  }, []);

  return (
    <div ref={root}>
      <div className="box" />
    </div>
  );
}
```

## Rich UX Website Building

Use Anime.js as the motion system when the task is to build a premium landing page, marketing site,
portfolio, or other immersive web experience. The bar here is not "add some animation"; it is to
make motion carry hierarchy, pacing, and interaction quality without sacrificing performance.

### Motion-First Principles

- Motion should explain structure and guide attention, not decorate static layouts.
- Favor scroll-triggered choreography with `onScroll()` and scoped cleanup over ad hoc observer logic.
- Treat typography as animated material: line, word, and character reveals should feel deliberate.
- Prefer SVG, layered DOM, and CSS variables for assets that need to move elegantly.
- Hover states should feel intentional: lift, parallax, line draw, morph, or spring response.
- Mobile motion should be simpler: shorter durations, smaller distances, fewer simultaneous effects.

### Website Stack Guidance

For greenfield website builds, prefer React with Next.js App Router and TypeScript. Use client
components for Anime.js-driven sections, and import only the modules the page needs when bundle size
matters.

Suggested structure:

```text
/app
  /(marketing)
    page.tsx
  /components
    Hero.tsx
    Nav.tsx
    AnimatedSection.tsx
    SVGLogo.tsx
  /hooks
    useAnimeScope.ts
  /lib
    animeUtils.ts
    animeScope.ts
  /sections
    About.tsx
    Services.tsx
    Work.tsx
    Contact.tsx
```

### Recommended Anime.js Features For Premium UI

- `createTimeline()` for hero orchestration, section sequencing, and multi-step interactions.
- `splitText()` for headline, paragraph, and label reveals with accessible cleanup.
- `onScroll()` for reveals, scrubbed narratives, and timeline synchronisation.
- `createLayout()` for filters, reordering, modal transitions, and layout-aware motion.
- `createDrawable()`, `morphTo()`, and `createMotionPath()` for logos, diagrams, and SVG storytelling.
- `createDraggable()` with `createSpring()` for tactile controls, card stacks, and sliders.
- WAAPI integration for simple, repetitive transform/opacity motion where offloading helps.

### Premium Site Section Pattern

Use a consistent motion structure across sections:

1. Navigation: logo draw, link stagger, menu open/close timeline.
2. Hero: text reveal, layered media motion, CTA entrance, subtle background movement.
3. Narrative sections: one timeline per section, triggered when entering view.
4. Grid/list sections: staggered card entrances and hover interactions.
5. Timeline/testimonial sections: line drawing plus progressive reveals.
6. Footer: restrained link/icon motion, not a second hero.

### Reusable Recipes For Website Work

#### Premium Text Reveal

```javascript
import { createTimeline, splitText, stagger } from 'animejs';

const title = splitText('.hero-title', {
  words: true,
  chars: true,
  accessible: true,
});

createTimeline({ defaults: { ease: 'outExpo', duration: 1200 } })
  .add(title.words, {
    translateY: ['1.2em', 0],
    opacity: [0, 1],
    delay: stagger(60),
  })
  .add(title.chars, {
    filter: ['blur(8px)', 'blur(0px)'],
    delay: stagger(12),
    duration: 500,
  }, '<+150');
```

#### Scroll-Triggered Section Reveal

```javascript
import { animate, onScroll } from 'animejs';

animate('.story-panel', {
  translateY: [80, 0],
  opacity: [0, 1],
  ease: 'outCubic',
  duration: 900,
  autoplay: onScroll({
    target: '.story-panel',
    sync: 0.5,
  }),
});
```

#### SVG Logo Draw

```javascript
import { animate, createDrawable } from 'animejs';

animate(createDrawable('#logo path'), {
  draw: ['0 0', '0 1'],
  ease: 'inOutSine',
  duration: 1800,
});
```

#### Layout Transition For Filtered Grids

```javascript
import { createLayout } from 'animejs';

const layout = createLayout('.projects-grid', {
  duration: 700,
  ease: 'inOutExpo',
});

layout.record();
applyProjectFilter();
layout.animate();
```

#### React Scope Pattern For Sections

```jsx
'use client';

import { useEffect, useRef } from 'react';
import { animate, createScope, stagger } from 'animejs';

export function AnimatedSection() {
  const rootRef = useRef(null);

  useEffect(() => {
    if (!rootRef.current) return;

    const scope = createScope({ root: rootRef.current }).add(() => {
      animate('.nav-link', {
        y: [16, 0],
        opacity: [0, 1],
        delay: stagger(80),
        ease: 'outExpo',
      });
    });

    return () => scope.revert();
  }, []);

  return <section ref={rootRef} />;
}
```

### Creative Direction Rules

- Avoid generic stock-photo-first design when the page is meant to feel premium.
- Prefer assets that can animate well: SVG logos, layered illustrations, isolated foreground subjects,
  procedural backgrounds, and graphics with clear depth.
- Ask how each major asset can reveal, draw, morph, parallax, or respond to input before settling on a static placement.

### Delivery Standards For Website Builds

- Respect `prefers-reduced-motion`; disable or simplify all major animation systems when requested.
- Keep animation setup scoped and reversible with `createScope()` and `revert()`.
- Prefer transforms and opacity over layout-affecting properties.
- Reduce stagger counts, distances, and scrub intensity on small screens.
- Keep animation code reusable instead of scattering ad hoc logic across components.
- Use Anime.js v4 APIs and imports consistently; avoid legacy v3 patterns unless the codebase already uses them.

## Bundle Sizes (Minified + Gzipped)

| Module | Size |
|--------|------|
| Full Bundle | ~24.5 KB |
| Timer | ~5.6 KB |
| Animation | +5.2 KB |
| Timeline | +0.55 KB |
| Animatable | +0.4 KB |
| Draggable | +6.4 KB |
| Scroll | +4.3 KB |
| Scope | +0.22 KB |
| SVG | ~0.35 KB |
| Stagger | +0.48 KB |
| Spring | ~0.52 KB |
| WAAPI | ~3.5 KB |

## Additional Resources

- Official Documentation: https://animejs.com/documentation
- Easing Editor: https://animejs.com/easing-editor
- CodePen Examples: https://codepen.io/collection/Poerqa
- GitHub: https://github.com/juliangarnier/anime

For detailed API parameters, code examples, and advanced patterns, see the references files:
- `references/api-reference.md` - Complete API documentation
- `references/examples.md` - Common animation patterns and recipes
