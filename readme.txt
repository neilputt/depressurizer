Depressurizer
for v0.6.0.0

SUMMARY

	Depressurizer is a program aimed at making it a bit easier to manage large
	Steam game libraries.

	In addition to providing a way to quickly and easily modify games' assigned
	categories, it also lets you mark them as Favorites or as hidden.

	Depressurizer can also autocategorize your games for you. Currently, it	does
	so based on data from that games' Steam store pages. It can use genres,
	store categories (like "Single-Player" and "Steam Cloud") or tags.

	It also saves your configuration information independently of Steam,
	providing an automatic backup in the event that Steam loses your
	configuration.

REQUIREMENTS

	Depressurizer requires the .NET Framework 4.5.1.

	It must be run on the same computer on which you use Steam, or one one of
	the computers on which you use Steam.

USAGE GUIDE

	GETTING STARTED

		Download the latest version of Depressurizer from the project's release
		page: https://github.com/rallion/depressurizer/releases

		The first time you run Depressurizer, it will ask you for your Steam
		directory. If it is not automatically and correctly detected, fill this
		in.

		Next, it will ask you to set up a profile. The easiest thing to do here
		is to simply select your profile from the "Select User" list and click
		OK.

		After a moment, you should see the game list fill up with all your
		games. You can now categorize them as you wish.

		When you are ready to save your changes, you MUST FIRST COMPLETELY CLOSE
		STEAM. You can this by clicking on Steam > Exit in the client, or by
		right clicking the Steam icon in your system tray and clicking Exit.

		Once Steam is closed, all you need to do is click on File > Save in
		Depressurizer. This will save your profile and, if you haven't changed
		any settings, will also automatically update your Steam config files
		with your changes. When you re-open Steam, your games should be
		organized.

		By default, Depressurizer will automatically load and update your
		profile the next time you launch the program.

	MANUAL CATEGORIZATION

		There are several ways to manually modify your games within
		Depressurizer.

		1) The Game Panel

		Changes made to the checkboxes at the bottom of the screen will
		automatically apply to ALL selected games. The checkboxes will update to
		reflect the current categories of the selected games.

		Entering text and clicking the "Add Category and Assign" button will
		create the entered category if it does not exist, and then assign all
		selected games to it.

		2) Drag and Drop

		If you select games in the list, and drag them to a category in the list
		on the left, you can add them to the selected category. You can drag
		them to "favorites" to set them as favorites, or to Uncategorized to
		clear their categories. 

		If you hold Ctrl when you drag items, you can remove them from the
		selected category instead of adding them.

		3) Context menu

		If you right click on the game list, there are options to add
		categories, remove categories, or alter the Favorite setting for the
		selected games.

	AUTOCATEGORIZATION

		Autocategorization in Depressurizer is based around different schemes
		that determine what categories to add to (or remove from) each game.
		These schemes are configurable, and are referred to as "AutoCats".

		You can autocategorize some of your games by selecting them and clicking
		the Autocategorize button below the game list. This will apply the
		AutoCat selected in the list below the button.

		You can autocategorize all games by using the "Autocat All" item in the
		Tools menu.

		To modify, delete or create new AutoCats, click the "Edit AutoCats..."
		item in the Profile menu.

		There are currently three types of AutoCat:

		Genre: This type autocategorizes games based on the genres it is
		assigned in the Steam store. It has several configuration options.

			Prefix (optional): This is just a text prefix added to the beginning
			of all genre names assigned by this scheme.

			Max Categories: This is the maximum number of categories that will
			be assigned to each game. If a particular game has more categories,
			they will be ignored. 0 indicates no maximum.

			Remove Others: This will remove other categories ONLY if they could
			potentially be added by this scheme. If a game already belongs to a
			category that has the name of a genre, with the Prefix, it will be
			removed before new categories are added to it.

			Ignored Genres: If you don't want a particular genre to be added as
			a category, select it here.

		Flags: This refers to the items on the right-hand side of the Steam
		Store pages that indicate certain features. For example, all games with
		the "Local Co-op" feature listed will be placed into a "Local Co-op"
		category.

			Prefix (optional): This is just a text prefix added to the beginning
			of all genre names assigned by this scheme.

			Included Flags: Only the items selected in this list will be used.

		Tags: This refers to the user-created tags. There are many more tags
		than there are genres or flags, so there are some options here to limit
		the ones you have to deal with.

			Prefix (optional): This is just a text prefix added to the beginning
			of all genre names assigned by this scheme.

			Max categories per game: This is the maximum number of categories
			that will be assigned to each game. 0 indicates no maximum.

			Included tags: These are the tags you can have added to your games
			as categories. Only the checked tags will be used. These tags are
			obtained by scanning the built-in game database. Each tag has a
			popularity score, shown in brackets after the name.

			List options: These options affect the tags that show up in the
			list, and the order that they show up in. Click "Rebuild" to update
			the list with the new settings. These settings will not affect which
			categories are actually added to games when the autocategorization
			is performed, but they may limit the tags that you have to choose
			from. They aim to mitigate the difficulty of dealing with a huge
			list of tags.

				Minimum tag score: Any tags with a lower score than this value
				will not appear in the list. Each tag's score may depend on the
				other options in this section.

				Weighting factor: This determines how the tags' popularity
				scores are calculated. With this set to 1.0, each tag's score is
				simply the number of times the tag appears across your library.
				With higher weighting factor values, tags that appear earlier in
				games' tag list will be given higher scores. There is a detailed
				example of exactly how this works in the FAQ at the bottom of
				this readme.

				Tags per game: The number of tags to scan in per game. 0 tells
				the program to scan all tags for each game. Limiting this can
				hide some infrequently-applied tags.

				Sort by score: Sorts tags by popularity so the more popular tags
				appear first. Otherwise, they will be sorted alphabetically.

				Exclude genres: Remove Steam genre names (Action, Indie,
				Strategy, etc.) from the tag list.

				Owned Only: Only scan the games that you own. Recommended. With
				this turned off, you will see all tags for every game in the
				database.

	DEFINITIONS OF TERMS AND PROCEDURES

		When you UPDATE your game list, the program is updating your library of
		owned games. It will do this either by accessing local Steam config
		files or by going to your Steam Community profile site, depending on
		your settings. This does not alter any categories, it only adds games to
		your list.

		When you IMPORT from Steam, the program is loading category and other
		information from your Steam config file. This is not guaranteed to have
		entries for all your games, but it includes data for any game that is
		currently categorized, favorited, or hidden. Note that if Steam is
		running, the imported data may not be up to date. This step is also
		where your non-Steam games are loaded, if you have them enabled.

		When you SAVE, you are saving your Depressurizer profile data. By
		default, this also exports to Steam, but this can be disabled in your
		profile settings.

		When you EXPORT, you are manually pushing your data to Steam. You should
		close Steam before doing this.

FAQ / TROUBLESHOOTING

	Will this mess up my Steam / get me VAC banned?

		No. The only things that Depressurizer does is to write to your
		configuration files, and it doesn't do anything that you couldn't do
		using the client itself.

	Why does my profile need to be public?

		If you are using the local update option in the profile settings, it
		does not. If you are only using the web update, the program needs your
		profile to be public in order to access your game list.

	Why are some of my games missing, even after I updated my game list?

		It is difficult to precisely determine the exact set of games that show
		up in the Steam client. The program does the best job I've been able to
		get it to do so far. If a game is (for some reason) in your game list
		without your account having a relevant license assigned to it, the local
		update will not pick it up. If the game does not show up on your
		community profile page, the web update will not pick it up. If a game is
		marked as DLC (or anything non-game-like) in the database, it will not
		get picked up by either of these methods. 

		To get unlisted games to show up in the program, you can add them
		manually by clicking the "Add Game" button.

		You can also add them to any category within Steam, then close Steam,
		then do an Import in Depressurizer. Depending on the problem, this may
		only work if the "Bypass auto-ignore..." option in the profile options
		screen is enabled.

	Why do I have extra things like DLC in my game list?

		The program relies on its database to filter out non-game entries. If
		that database is wrong, extra items might show up. You might also have
		"Don't ignore unknown apps" in the profile settings "Ignored Games" tab
		checked, which can let in a lot of extra stuff.

		The program trusts that any game that it finds in your Steam config file
		should be there, so if something gets in there (this can easily happen
		with games that are only in your library temporarily for any reason) it
		will show up in Depressurizer after an import.

		To remove a specific item, just select it and click "Delete Game". This
		will remove it from your list and (by default) ignore it going forward.

	Why do some of my games not autocategorize at all?

		The program database might be out of date. Also, the program relies on
		the Steam Store data for autocategorization info. Sometimes, a game that
		is on your account might not HAVE a Store page any more, so the database
		won't have any data on it.

	How do I update the database myself?

		Click on Tools > Database Editor. Click "Update App Info" to pull the
		latest information from the local Steam cache file (by default this is
		done on program start anyway). Click "Fetch List" to get a list of all
		Steam apps. Then, click "Scrape Unscraped". This might take some time.
		If you click Stop (NOT CANCEL) it will save what you've gotten so far
		and you can come back later. Click File > Save to save your changes.

	What exactly does the weighting factor on the tags autocat dialog do?

		Okay. The tag scanner runs through all of your games, and for each game
		it runs through all of your tags. As it goes, it makes a list of the
		tags it finds, and for each one, it keeps track of its "popularity
		score." Each time it sees a tag, it adds a value to its popularity
		score. If the weighting factor is set to 1.0, this value is always 1, so
		the score is just the number of times the scan encountered that tag.

		However, the first tags assigned to a game are the more popular ones, so
		you might want to give them more weight by increasing the weighting
		factor. The first tag for each game will always add the weighting factor
		to that tag's popularity score, and the last tag will always add 1. The
		tags in the middle add scores that linearly decrease before those
		values. For example, if a game has five tags (A, B, C, D, E), and the
		weight factor is set to 3, the scores added to each of those five tags
		will be: 3.0, 2.5, 2.0, 1.5, 1.0.
