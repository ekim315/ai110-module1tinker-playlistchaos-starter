Fix at least four issues
Make improvements based on your investigation.

For each fix:

Identify the source of the issue
Decide whether to accept or adjust the AI assistant's suggestions
Update the code
Add a short comment describing the fix
Your fixes may involve logic, calculations, search behavior, playlist grouping, lucky pick behavior, or anything else you discover.

-first potential bug: lucky pick feature, cannot select a song from the "mixed" playlist

line 190 in playlist_logic.py. add "playlists.get("Mixed", [])" in the else statement to include songs in the mixed playlist.

-second potential bug: hype ratio doesn't change when i move the hype energy levels, always 1.0

line 119-120 in playlist_logic.py: the variable total = len(hype) but in line 120, hype ratio uses the same value to divide them together, which will always result in 1.0 since it's dividing itself. 

-third potential bug: only complete name of artist returns the song. ex) putting weeknd won't show up unless you put "the" weeknd

line 171 "if value and value in q:" this only checks if the artist value is in the inputted query, instead of other way around.

-4th potential bug: lucky pick crashes if there are no songs in that playlist

line 194-198 has the fn "random_choice_or_none". it doesn't have the edge case in which songs is empty. added a if statement to account for when songs is empty.
