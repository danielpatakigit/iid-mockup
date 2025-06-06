<!-- src/routes/+page.svelte -->
<script>
	import { onMount } from 'svelte'
	import { blur } from 'svelte/transition'

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

	const languages = { en: 'English', de: 'Deutsch', hu: 'Magyar' }
	const lectureHalls = [
		'Audimax Center',
		'GM 1 Audi.Max.',
		'GM 2 Hörsaal BE01',
		'FH 1 Hörsaal 1',
		'FH 6 Hörsaal 1',
		'FH 8 Hörsaal 1',
	]
	const summaryData = {
		en: "Professor David Malan introduces CS50, Harvard's computer science course. He shares his personal journey from government studies to computer science, emphasizing how programming is a general-purpose problem-solving skill applicable across many fields. He warns students that the course will feel like 'drinking from a fire hose' due to the large amount of information, but encourages them that even this single CS course can be valuable regardless of their major.",
		de: "Professor David Malan stellt CS50 vor, Harvards Informatikkurs. Er teilt seine persönliche Reise von Regierungsstudien zur Informatik mit und betont, wie Programmierung eine allgemeine Problemlösungsfähigkeit ist, die in vielen Bereichen anwendbar ist. Er warnt die Studenten, dass sich der Kurs wie 'aus einem Feuerschlauch trinken' anfühlen wird aufgrund der großen Informationsmenge, ermutigt sie aber, dass selbst dieser einzelne CS-Kurs wertvoll sein kann, unabhängig von ihrem Hauptfach.",
		hu: "David Malan professzor bemutatja a CS50-et, a Harvard informatika kurzusát. Megosztja személyes útját a kormányzati tanulmányoktól az informatikáig, hangsúlyozva, hogy a programozás általános célú problémamegoldó készség, amely sok területen alkalmazható. Figyelmezteti a hallgatókat, hogy a kurzus úgy fog érezni, mint 'tűzoltótömlőből inni' a nagy mennyiségű információ miatt, de bátorítja őket, hogy még ez az egyetlen informatikai kurzus is értékes lehet, függetlenül a szakjuktól.",
	}

	// State management
	let currentView = $state('login')
	let username = $state(''),
		password = $state(''),
		emailAddress = $state('')
	let selectedLectureHall = $state(''),
		selectedLanguage = $state('en')
	let textSize = $state(11),
		backgroundTransparency = $state(70)
	let currentTranscriptIndex = $state(0),
		mouseX = $state(0),
		mouseY = $state(0)
	let focusedElement = $state(null),
		videoElement = $state()
	let transcriptInterval

	const currentTranscript = $derived(transcriptData[selectedLanguage] || transcriptData.en)
	const currentSummary = $derived(summaryData[selectedLanguage] || summaryData.en)

	onMount(() => {
		const handleMouseMove = (e) => {
			mouseX = e.clientX
			mouseY = e.clientY
		}
		document.addEventListener('mousemove', handleMouseMove)
		return () => {
			document.removeEventListener('mousemove', handleMouseMove)
			if (transcriptInterval) clearInterval(transcriptInterval)
		}
	})

	function handleLogin() {
		if (username.trim() && password.trim()) {
			currentView = 'lectureSelection'
		}
	}

	function handleLectureHallSelection(hall) {
		selectedLectureHall = hall
		currentView = 'lecture'
		setTimeout(() => startTranscriptTracking(), 100)
	}

	function startTranscriptTracking() {
		if (transcriptInterval) clearInterval(transcriptInterval)
		transcriptInterval = setInterval(() => {
			if (videoElement && !videoElement.paused) {
				const videoTime = videoElement.currentTime
				if (videoTime >= 115) {
					currentTranscriptIndex = 0
					return
				}
				for (let i = 0; i < currentTranscript.length; i++) {
					if (
						videoTime >= currentTranscript[i].startTime &&
						(i === currentTranscript.length - 1 || videoTime < currentTranscript[i + 1].startTime)
					) {
						currentTranscriptIndex = i
						break
					}
				}
			}
		}, 100)
	}

	function handleVideoCanPlay() {
		if (videoElement && currentView === 'lecture') {
			videoElement.play().catch(() => console.log('Autoplay prevented'))
			startTranscriptTracking()
		}
	}

	function logout() {
		currentView = 'login'
		username = password = selectedLectureHall = emailAddress = ''
		currentTranscriptIndex = 0
		if (videoElement) {
			videoElement.pause()
			videoElement.currentTime = 0
		}
		if (transcriptInterval) {
			clearInterval(transcriptInterval)
			transcriptInterval = null
		}
	}

	function handleExport() {
		if (emailAddress.trim()) {
			alert(`Transcript and summary sent to ${emailAddress}!`)
			currentView = 'lecture'
		}
	}

	function setFocus(id) {
		focusedElement = id
	}
	function clearFocus() {
		focusedElement = null
	}
</script>

<svelte:head><title>EduLens AR Glasses</title></svelte:head>

<div class="w-screen h-screen bg-black relative overflow-hidden" style="aspect-ratio: 16/9;">
	<!-- Eye-tracking cursor -->
	<div
		class="fixed pointer-events-none z-50 w-12 h-12 rounded-full bg-blue-400 opacity-30 transition-all duration-75 ease-out"
		style="left: {mouseX - 24}px; top: {mouseY - 24}px;"
	></div>

	{#if currentView === 'login'}
		<div
			class="w-full h-full flex items-center justify-center bg-gradient-to-br from-blue-900 to-purple-900"
		>
			<div
				class="bg-white/10 backdrop-blur-md rounded-lg p-8 w-96 border border-white/20 {focusedElement ===
				'loginForm'
					? 'ring-2 ring-blue-400'
					: ''}"
				onmouseenter={() => setFocus('loginForm')}
				onmouseleave={clearFocus}
			>
				<div class="text-center mb-6">
					<h1 class="text-3xl font-bold text-white mb-2">EduLens</h1>
					<p class="text-blue-200">AR Learning Assistant</p>
				</div>
				<div class="space-y-4">
					<div>
						<label class="block text-white text-sm font-medium mb-2">Username</label>
						<input
							type="text"
							bind:value={username}
							placeholder="Enter your username"
							class="w-full px-3 py-2 bg-white/20 border border-white/30 rounded-md text-white placeholder-white/60 focus:outline-none focus:ring-2 focus:ring-blue-400"
						/>
					</div>
					<div>
						<label class="block text-white text-sm font-medium mb-2">Password</label>
						<input
							type="password"
							bind:value={password}
							placeholder="Enter your password"
							class="w-full px-3 py-2 bg-white/20 border border-white/30 rounded-md text-white placeholder-white/60 focus:outline-none focus:ring-2 focus:ring-blue-400"
						/>
					</div>
					<button
						onclick={handleLogin}
						class="w-full bg-blue-600 hover:bg-blue-700 text-white font-medium py-2 px-4 rounded-md transition-colors focus:outline-none focus:ring-2 focus:ring-blue-400"
					>
						Sign In
					</button>
				</div>
			</div>
		</div>
	{/if}

	{#if currentView === 'lectureSelection'}
		<div
			class="w-full h-full flex items-center justify-center bg-gradient-to-br from-green-900 to-blue-900"
		>
			<div
				class="bg-white/10 backdrop-blur-md rounded-lg p-8 w-96 border border-white/20 {focusedElement ===
				'lectureSelection'
					? 'ring-2 ring-blue-400'
					: ''}"
				onmouseenter={() => setFocus('lectureSelection')}
				onmouseleave={clearFocus}
			>
				<div class="text-center mb-6">
					<h2 class="text-2xl font-bold text-white mb-2">Select Lecture Hall</h2>
					<p class="text-blue-200">Choose your current location</p>
				</div>
				<div class="space-y-3">
					{#each lectureHalls as hall}
						<button
							onclick={() => handleLectureHallSelection(hall)}
							class="w-full text-left px-4 py-3 bg-white/20 hover:bg-white/30 border border-white/30 rounded-md text-white transition-colors focus:outline-none focus:ring-2 focus:ring-blue-400"
						>
							{hall}
						</button>
					{/each}
				</div>
				<button
					onclick={logout}
					class="w-full mt-6 bg-red-600 hover:bg-red-700 text-white font-medium py-2 px-4 rounded-md transition-colors focus:outline-none focus:ring-2 focus:ring-red-400"
				>
					Logout
				</button>
			</div>
		</div>
	{/if}

	{#if currentView === 'lecture'}
		<div class="w-full h-full relative">
			<video
				bind:this={videoElement}
				class="w-full h-full object-cover"
				loop
				autoplay
				oncanplay={handleVideoCanPlay}
				onended={() => (currentTranscriptIndex = 0)}
			>
				<source src="/src/lib/video.mp4" type="video/mp4" />
			</video>

			{#if currentTranscript[currentTranscriptIndex]}
				<div
					class="absolute bottom-16 left-1/2 transform -translate-x-1/2 max-w-7xl px-6"
					style="background-color: rgba(0, 0, 0, {backgroundTransparency /
						100}); border-radius: 8px;"
				>
					{#key currentTranscriptIndex}
						<p
							in:blur
							class="text-white font-medium text-center py-4 px-6"
							style="font-size: {textSize}pt; text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.8);"
						>
							{currentTranscript[currentTranscriptIndex].text}
						</p>
					{/key}
				</div>
			{/if}

			<div class="absolute top-4 right-4 flex gap-3">
				<button
					onclick={() => (currentView = 'settings')}
					class="bg-blue-600/80 hover:bg-blue-700/80 text-white p-3 rounded-full backdrop-blur-sm transition-colors {focusedElement ===
					'settingsBtn'
						? 'ring-2 ring-blue-400'
						: ''}"
					onmouseenter={() => setFocus('settingsBtn')}
					onmouseleave={clearFocus}
				>
					<svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="M10.325 4.317c.426-1.756 2.924-1.756 3.35 0a1.724 1.724 0 002.573 1.066c1.543-.94 3.31.826 2.37 2.37a1.724 1.724 0 001.065 2.572c1.756.426 1.756 2.924 0 3.35a1.724 1.724 0 00-1.066 2.573c.94 1.543-.826 3.31-2.37 2.37a1.724 1.724 0 00-2.572 1.065c-.426 1.756-2.924 1.756-3.35 0a1.724 1.724 0 00-2.573-1.066c-1.543.94-3.31-.826-2.37-2.37a1.724 1.724 0 00-1.065-2.572c-1.756-.426-1.756-2.924 0-3.35a1.724 1.724 0 001.066-2.573c-.94-1.543.826-3.31 2.37-2.37.996.608 2.296.07 2.572-1.065z"
						/>
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="M15 12a3 3 0 11-6 0 3 3 0 016 0z"
						/>
					</svg>
				</button>
				<button
					onclick={() => (currentView = 'export')}
					class="bg-green-600/80 hover:bg-green-700/80 text-white p-3 rounded-full backdrop-blur-sm transition-colors {focusedElement ===
					'exportBtn'
						? 'ring-2 ring-green-400'
						: ''}"
					onmouseenter={() => setFocus('exportBtn')}
					onmouseleave={clearFocus}
				>
					<svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="M12 19l9 2-9-18-9 18 9-2zm0 0v-8"
						/>
					</svg>
				</button>
				<button
					onclick={logout}
					class="bg-red-600/80 hover:bg-red-700/80 text-white p-3 rounded-full backdrop-blur-sm transition-colors {focusedElement ===
					'logoutBtn'
						? 'ring-2 ring-red-400'
						: ''}"
					onmouseenter={() => setFocus('logoutBtn')}
					onmouseleave={clearFocus}
				>
					<svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="M17 16l4-4m0 0l-4-4m4 4H7m6 4v1a3 3 0 01-3 3H6a3 3 0 01-3-3V7a3 3 0 013-3h4a3 3 0 013 3v1"
						/>
					</svg>
				</button>
			</div>
		</div>
	{/if}

	{#if currentView === 'settings'}
		<div class="w-full h-full flex items-center justify-center bg-black/50 backdrop-blur-sm">
			<div
				class="bg-white/10 backdrop-blur-md rounded-lg p-8 w-96 border border-white/20 {focusedElement ===
				'settingsPanel'
					? 'ring-2 ring-blue-400'
					: ''}"
				onmouseenter={() => setFocus('settingsPanel')}
				onmouseleave={clearFocus}
			>
				<div class="text-center mb-6">
					<h2 class="text-2xl font-bold text-white mb-2">Subtitle Settings</h2>
				</div>
				<div class="space-y-6">
					<div>
						<label class="block text-white text-sm font-medium mb-2">Language</label>
						<select
							bind:value={selectedLanguage}
							class="w-full px-3 py-2 bg-white/20 border border-white/30 rounded-md text-white focus:outline-none focus:ring-2 focus:ring-blue-400"
						>
							{#each Object.entries(languages) as [code, name]}
								<option value={code} class="bg-gray-800">{name}</option>
							{/each}
						</select>
					</div>
					<div>
						<label class="block text-white text-sm font-medium mb-2">Text Size: {textSize}pt</label>
						<input
							type="range"
							min="8"
							max="14"
							bind:value={textSize}
							class="w-full h-2 bg-white/20 rounded-lg appearance-none cursor-pointer focus:outline-none focus:ring-2 focus:ring-blue-400"
						/>
					</div>
					<div>
						<label class="block text-white text-sm font-medium mb-2"
							>Background Opacity: {backgroundTransparency}%</label
						>
						<input
							type="range"
							min="0"
							max="100"
							bind:value={backgroundTransparency}
							class="w-full h-2 bg-white/20 rounded-lg appearance-none cursor-pointer focus:outline-none focus:ring-2 focus:ring-blue-400"
						/>
					</div>
					<div class="mt-6">
						<label class="block text-white text-sm font-medium mb-2">Preview</label>
						<div
							class="p-4 rounded-md"
							style="background-color: rgba(0, 0, 0, {backgroundTransparency / 100});"
						>
							<p
								class="text-white text-center"
								style="font-size: {textSize}pt; text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.8);"
							>
								Sample subtitle text
							</p>
						</div>
					</div>
				</div>
				<button
					onclick={() => (currentView = 'lecture')}
					class="w-full mt-6 bg-blue-600 hover:bg-blue-700 text-white font-medium py-2 px-4 rounded-md transition-colors focus:outline-none focus:ring-2 focus:ring-blue-400"
				>
					Save & Close
				</button>
			</div>
		</div>
	{/if}

	{#if currentView === 'export'}
		<div class="w-full h-full flex items-center justify-center bg-black/50 backdrop-blur-sm">
			<div
				class="bg-white/10 backdrop-blur-md rounded-lg p-8 w-96 max-h-[80vh] overflow-y-auto border border-white/20 {focusedElement ===
				'exportPanel'
					? 'ring-2 ring-blue-400'
					: ''}"
				onmouseenter={() => setFocus('exportPanel')}
				onmouseleave={clearFocus}
			>
				<div class="text-center mb-6">
					<h2 class="text-2xl font-bold text-white mb-2">Export Transcript</h2>
				</div>
				<div class="space-y-4">
					<div>
						<label class="block text-white text-sm font-medium mb-2">Email Address</label>
						<input
							type="email"
							bind:value={emailAddress}
							placeholder="Enter your email address"
							class="w-full px-3 py-2 bg-white/20 border border-white/30 rounded-md text-white placeholder-white/60 focus:outline-none focus:ring-2 focus:ring-blue-400"
						/>
					</div>
					<div>
						<label class="block text-white text-sm font-medium mb-2"
							>Full Transcript ({languages[selectedLanguage]})</label
						>
						<div class="bg-white/10 border border-white/30 rounded-md p-4 max-h-48 overflow-y-auto">
							<div class="space-y-2">
								{#each currentTranscript as segment}
									<p class="text-white text-sm leading-relaxed">
										<span class="text-blue-300 font-mono text-xs"
											>[{Math.floor(segment.startTime / 60)}:{String(
												Math.floor(segment.startTime % 60)
											).padStart(2, '0')}]</span
										>
										{segment.text}
									</p>
								{/each}
							</div>
						</div>
					</div>
					<div>
						<label class="block text-white text-sm font-medium mb-2"
							>AI Generated Summary ({languages[selectedLanguage]})</label
						>
						<div class="bg-white/10 border border-white/30 rounded-md p-4 max-h-32 overflow-y-auto">
							<p class="text-white text-sm leading-relaxed">{currentSummary}</p>
						</div>
					</div>
				</div>
				<div class="flex gap-3 mt-6">
					<button
						onclick={() => (currentView = 'lecture')}
						class="flex-1 bg-gray-600 hover:bg-gray-700 text-white font-medium py-2 px-4 rounded-md transition-colors focus:outline-none focus:ring-2 focus:ring-gray-400"
					>
						Cancel
					</button>
					<button
						onclick={handleExport}
						class="flex-1 bg-green-600 hover:bg-green-700 text-white font-medium py-2 px-4 rounded-md transition-colors focus:outline-none focus:ring-2 focus:ring-green-400"
					>
						Send to Email
					</button>
				</div>
			</div>
		</div>
	{/if}
</div>

<style>
	/* Custom styles for range inputs to make them more visible */
	input[type='range'] {
		-webkit-appearance: none;
		background: transparent;
	}

	input[type='range']::-webkit-slider-track {
		background: rgba(255, 255, 255, 0.2);
		height: 8px;
		border-radius: 4px;
	}

	input[type='range']::-webkit-slider-thumb {
		-webkit-appearance: none;
		height: 20px;
		width: 20px;
		border-radius: 50%;
		background: #3b82f6;
		cursor: pointer;
		border: 2px solid white;
		box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
	}

	input[type='range']::-moz-range-track {
		background: rgba(255, 255, 255, 0.2);
		height: 8px;
		border-radius: 4px;
		border: none;
	}

	input[type='range']::-moz-range-thumb {
		height: 20px;
		width: 20px;
		border-radius: 50%;
		background: #3b82f6;
		cursor: pointer;
		border: 2px solid white;
		box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
	}

	/* Ensure video covers full container */
	video {
		width: 100%;
		height: 100%;
		object-fit: cover;
	}

	/* Custom scrollbar for better visibility */
	::-webkit-scrollbar {
		width: 8px;
	}

	::-webkit-scrollbar-track {
		background: rgba(255, 255, 255, 0.1);
		border-radius: 4px;
	}

	::-webkit-scrollbar-thumb {
		background: rgba(255, 255, 255, 0.3);
		border-radius: 4px;
	}

	::-webkit-scrollbar-thumb:hover {
		background: rgba(255, 255, 255, 0.5);
	}
</style>
