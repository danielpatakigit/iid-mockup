# .gitignore

```
node_modules

# Output
.output
.vercel
.netlify
.wrangler
/.svelte-kit
/build

# OS
.DS_Store
Thumbs.db

# Env
.env
.env.*
!.env.example
!.env.test

# Vite
vite.config.js.timestamp-*
vite.config.ts.timestamp-*

```

# .npmrc

```
engine-strict=true

```

# jsconfig.json

```json
{
	"extends": "./.svelte-kit/tsconfig.json",
	"compilerOptions": {
		"allowJs": true,
		"checkJs": false,
		"moduleResolution": "bundler"
	}
	// Path aliases are handled by https://svelte.dev/docs/kit/configuration#alias
	// except $lib which is handled by https://svelte.dev/docs/kit/configuration#files
	//
	// If you want to overwrite includes/excludes, make sure to copy over the relevant includes/excludes
	// from the referenced tsconfig.json - TypeScript does not merge them in
}

```

# package.json

```json
{
	"name": "iid-mockup",
	"private": true,
	"version": "0.0.1",
	"type": "module",
	"scripts": {
		"dev": "vite dev",
		"build": "vite build",
		"preview": "vite preview",
		"prepare": "svelte-kit sync || echo ''"
	},
	"devDependencies": {
		"@sveltejs/adapter-vercel": "^5.6.3",
		"@sveltejs/kit": "^2.16.0",
		"@sveltejs/vite-plugin-svelte": "^5.0.0",
		"@tailwindcss/forms": "^0.5.9",
		"@tailwindcss/typography": "^0.5.15",
		"@tailwindcss/vite": "^4.0.0",
		"svelte": "^5.0.0",
		"tailwindcss": "^4.0.0",
		"vite": "^6.2.6"
	},
	"dependencies": {}
}

```

# README.md

```md
# sv

Everything you need to build a Svelte project, powered by [`sv`](https://github.com/sveltejs/cli).

## Creating a project

If you're seeing this, you've probably already done this step. Congrats!

\`\`\`bash
# create a new project in the current directory
npx sv create

# create a new project in my-app
npx sv create my-app
\`\`\`

## Developing

Once you've created a project and installed dependencies with `npm install` (or `pnpm install` or `yarn`), start a development server:

\`\`\`bash
npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
\`\`\`

## Building

To create a production version of your app:

\`\`\`bash
npm run build
\`\`\`

You can preview the production build with `npm run preview`.

> To deploy your app, you may need to install an [adapter](https://svelte.dev/docs/kit/adapters) for your target environment.

```

# src/app.css

```css
@import 'tailwindcss';
@plugin '@tailwindcss/forms';
@plugin '@tailwindcss/typography';

```

# src/app.html

```html
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="utf-8" />
		<link rel="icon" href="%sveltekit.assets%/favicon.png" />
		<meta name="viewport" content="width=device-width, initial-scale=1" />
		%sveltekit.head%
	</head>
	<body data-sveltekit-preload-data="hover">
		<div style="display: contents">%sveltekit.body%</div>
	</body>
</html>

```

# src/lib/index.js

```js
// place files you want to import through the `$lib` alias in this folder.

```

# src/lib/video.mp4

This is a binary file of the type: Binary

# src/routes/+layout.svelte

```svelte
<script>
	import '../app.css';
	
	let { children } = $props();
</script>

{@render children()}

```

# src/routes/+page.svelte

```svelte
<script>
	const transcriptData = {
		en: [
			{
				startTime: 0,
				text: 'to the intellectual enterprises of computer science and the art of programming. And this is Spot. And our thanks to our friends at 3D Cowboys for bringing him by class today. Perhaps a round of applause for our special Professor [INAUDIBLE].. My name is David Malan.',
			},
			{
				startTime: 18,
				text: "And I actually took this class, CS50, myself, some years ago. But I almost didn't. And I didn't because when I got to campus, as a first-year, I really gravitated toward things already familiar, things with which I was already comfortable, specifically, government.",
			},
			{
				startTime: 30,
				text: 'And I came in here thinking I was going to major or concentrate in government. And it was only once I got to sophomore year, fall semester, that some friends of mine were coming to this class called CS50 that was very much to beware at the time, in that it',
			},
			{
				startTime: 43,
				text: 'was an unfamiliar field to so many of us, myself included. But I got up the nerve to go over the threshold, sit in on the first class, just shop it, so to speak. And I was hooked. I found that homework was, for the first time, fun. And this was after having enrolled only because the professor let',
			},
			{
				startTime: 59,
				text: "me enroll pass/fail or [INAUDIBLE] because I didn't really think I could even cut it. But fast forward to five Mondays later in the semester, I actually switched to a letter grade, deciding, wow, this is actually something for me. And I say this because computer science, what",
			},
			{
				startTime: 72,
				text: "I didn't realize about it at the time, really is this very general purpose way of thinking and way of solving problems. And even if this is the only CS class you ever take, even if this is the only formal training you have in programming as a practical skill, it's just so darn applicable",
			},
			{
				startTime: 88,
				text: "to so many other fields-- the arts, humanities, social sciences, natural sciences, and beyond, and certainly within the STEM fields, themselves. That said, it's going to often feel a little something like this. This is from our friends at MIT, down the road, which is one of their hacks",
			},
			{
				startTime: 102,
				text: 'whereby they connected a fire hydrant to a drinking fountain, with a little sign up there that says, "GETTING AN EDUCATION FROM MIT IS LIKE DRINKING FROM A FIRE HOSE," which is to say that it\'s going to feel, quite often, in this class, too, that there\'s just a lot of information.',
			},
		],
		de: [
			{
				startTime: 0,
				text: 'in die intellektuellen Unternehmungen der Informatik und die Kunst des Programmierens. Und das ist Spot. Und unser Dank geht an unsere Freunde von 3D Cowboys, dass sie ihn heute zur Klasse gebracht haben. Vielleicht ein Applaus für unseren besonderen Professor [UNVERSTÄNDLICH].. Mein Name ist David Malan.',
			},
			{
				startTime: 18,
				text: 'Und ich habe diese Klasse, CS50, selbst vor einigen Jahren besucht. Aber ich hätte es fast nicht getan. Und ich tat es nicht, weil ich, als ich auf den Campus kam, als Erstsemester, wirklich zu Dingen hingezogen wurde, die bereits vertraut waren, mit denen ich bereits vertraut war, speziell Regierung.',
			},
			{
				startTime: 30,
				text: 'Und ich kam hierher und dachte, ich würde Regierung als Hauptfach oder Schwerpunkt wählen. Und erst als ich im zweiten Jahr war, Herbstsemester, kamen einige meiner Freunde zu dieser Klasse namens CS50, die damals sehr zu hüten war, da es',
			},
			{
				startTime: 43,
				text: 'ein unbekanntes Feld für so viele von uns war, mich eingeschlossen. Aber ich fasste den Mut, über die Schwelle zu gehen, bei der ersten Klasse zu sitzen, sie sozusagen auszuprobieren. Und ich war fasziniert. Ich fand, dass Hausaufgaben zum ersten Mal Spaß machten. Und das, nachdem ich mich nur eingeschrieben hatte, weil der Professor mich ließ',
			},
			{
				startTime: 59,
				text: 'mich bestehen/nicht bestehen oder [UNVERSTÄNDLICH] einschreiben, weil ich wirklich nicht dachte, dass ich es schaffen könnte. Aber fünf Montage später im Semester wechselte ich tatsächlich zu einer Buchstabennote und entschied, wow, das ist wirklich etwas für mich. Und ich sage das, weil Informatik, was',
			},
			{
				startTime: 72,
				text: 'ich damals nicht darüber wusste, wirklich diese sehr allgemeine Art des Denkens und des Problemlösens ist. Und auch wenn das die einzige CS-Klasse ist, die Sie jemals nehmen, auch wenn das die einzige formale Ausbildung ist, die Sie im Programmieren als praktische Fähigkeit haben, ist es einfach so verdammt anwendbar',
			},
			{
				startTime: 88,
				text: 'auf so viele andere Bereiche-- die Künste, Geisteswissenschaften, Sozialwissenschaften, Naturwissenschaften und darüber hinaus, und sicherlich innerhalb der STEM-Bereiche selbst. Das gesagt, wird es sich oft ein wenig so anfühlen. Das ist von unseren Freunden am MIT, die Straße runter, was einer ihrer Hacks ist',
			},
			{
				startTime: 102,
				text: 'wobei sie einen Feuerhydranten an einen Trinkbrunnen anschlossen, mit einem kleinen Schild da oben, das sagt: "EINE AUSBILDUNG VOM MIT ZU BEKOMMEN IST WIE AUS EINEM FEUERSCHLAUCH ZU TRINKEN", was bedeutet, dass es sich sehr oft in dieser Klasse auch so anfühlen wird, dass es einfach viele Informationen gibt.',
			},
		],
		hu: [
			{
				startTime: 0,
				text: 'a számítástechnika intellektuális vállalkozásaiba és a programozás művészetébe. És ez Spot. És köszönjük barátainknak a 3D Cowboys-tól, hogy elhozták ma az órára. Talán egy taps a különleges Professzorunknak [ÉRTHETETLEN].. A nevem David Malan.',
			},
			{
				startTime: 18,
				text: 'És én magam is elvégeztem ezt az órát, a CS50-et, néhány évvel ezelőtt. De majdnem nem tettem meg. És azért nem tettem meg, mert amikor a kampuszra érkeztem, elsőévesként, igazán a már ismerős dolgok felé vonzódtam, olyan dolgok felé, amelyekkel már kényelmes voltam, konkrétan a kormányzat.',
			},
			{
				startTime: 30,
				text: 'És ide jöttem arra gondolva, hogy kormányzást fogok főszakként vagy koncentrációként választani. És csak amikor a második évben voltam, őszi félévben, néhány barátom eljött erre az órára, amit CS50-nek hívtak, ami akkoriban nagyon óvatos volt, abban hogy',
			},
			{
				startTime: 43,
				text: 'ismeretlen terület volt sokunk számára, engem is beleértve. De összeszedtem a bátorságot, hogy átlépjem a küszöböt, beüljek az első órára, úgymond kipróbáljam. És lenyűgözött. Azt találtam, hogy a házi feladat először volt szórakoztató. És ez azután történt, hogy csak azért iratkoztam be, mert a professzor engedte',
			},
			{
				startTime: 59,
				text: 'hogy megfelelt/nem felelt vagy [ÉRTHETETLEN] módon iratkozzam be, mert nem igazán gondoltam, hogy meg tudom csinálni. De öt hétfővel később a félévben, valójában átváltottam betű osztályzatra, úgy döntve, hűha, ez tényleg nekem való. És ezt azért mondom, mert a számítástechnika, amit',
			},
			{
				startTime: 72,
				text: 'akkor nem realizáltam róla, valójában ez a nagyon általános célú gondolkodási mód és problémamegoldási mód. És még ha ez az egyetlen informatika óra, amit valaha veszel, még ha ez az egyetlen formális képzés, amid van a programozásban mint gyakorlati készség, egyszerűen annyira alkalmazható',
			},
			{
				startTime: 88,
				text: 'annyi más területre-- a művészetek, bölcsészettudományok, társadalomtudományok, természettudományok és azon túl, és természetesen a STEM területeken belül is. Ennek ellenére gyakran egy kicsit így fog érezni. Ez a barátainktól származik az MIT-ről, az út végén, ami az egyik hackjük',
			},
			{
				startTime: 102,
				text: 'amellyel egy tűzcsapot kötöttek egy ivókúthoz, egy kis táblával ott fent, ami azt mondja: "OKTATÁST KAPNI AZ MIT-TŐL OLYAN, MINT TŰZOLTÓTÖMLŐBŐL INNI", ami azt jelenti, hogy gyakran úgy fog érezni, ebben az órában is, hogy egyszerűen sok az információ.',
			},
		],
	}
	// Languages
	const languages = {
		en: 'English',
		de: 'Deutsch',
		hu: 'Magyar',
	}

	// Lecture halls
	const lectureHalls = [
		'Audimax Center',
		'GM 1 Audi.Max.',
		'GM 2 Hörsaal BE01',
		'FH 1 Hörsaal 1',
		'FH 6 Hörsaal 1',
		'FH 8 Hörsaal 1',
	]
</script>

<video id="player" playsinline controls loop autoplay>
	<source src="/src/lib/video.mp4" type="video/webm" />

	<!-- Captions are optional -->
	<track kind="captions" default />
</video>

```

# static/favicon.png

This is a binary file of the type: Image

# svelte.config.js

```js
import adapter from '@sveltejs/adapter-vercel';

const config = { kit: { adapter: adapter() } };

export default config;

```

# vite.config.js

```js
import tailwindcss from '@tailwindcss/vite';
import { sveltekit } from '@sveltejs/kit/vite';
import { defineConfig } from 'vite';

export default defineConfig({
	plugins: [tailwindcss(), sveltekit()]
});

```

