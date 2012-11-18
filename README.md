Alia - a PyBorg with a difference
---------------------------------

Alia is a self-optimising Pyborg IRC Bot with the added ability to be taught via commands.

The original Pyborg was written by Tom Morton and Sébastien Dailly. It's a simple python Markov chain driven bot (similar to MegaHAL) with the unique ability to learn speech patterns by figure out which words go togeher well. This gives it the ability to generate replies on it's own aswell as repeating previously learned responses.

What sets Alia apart from the default pyborg bot are the following:
* Alia has bash scripts to start her quietly and keep small logs which only report when bugs happen.
* Alia saves her dictionary/word list every 2 hours, optimises it every 5 hours and rebuild it every 3 days to keep it error free.
* Alia strips common error causing input (like urls and control codes) by default to avoid dictionary corruption.
* Alia doesn't lowercase learned data at all. She'll respond in the same way as she learned it!
* Alia doesn't mangle emoticons (smileys) or punctuation. She also correct I and I contractions and capitalizes the first letter of every sentence.
* Alia doesn't mangle nicknames anymore either. She will only replace her own nick in learned responses.
* Alia is utf-8 compliant and can be used with most locales!
* Alia logs all private conversation (except with masters) in a physical form (example: http://user.gigirc.com/~brenton/logs/)
* Alia can be talked to with IM clients using bitlbee and pyborg-im.py! (Example: http://www.facebook.com/alia.smart)
* Alia can be taught multiple random responses with the !teach or !learn command.
* Alia's new taught responses can be searched with !find and forgotten with with !forget.
* Alia can be copied over an existing pyborg copy and will uses the same dictionaries/wordlists as the old one.
* Alia can respond to and learn actions! This can be done via the learing system or by observing other user's actions.
And many more! (See ChangeLog for complete list)

New Commands
------------

To teach Alia a response, use the !learn or !teach command with the trigger and response seperated by an |. Spaces don't matter, but the length is limited to the standard IRC message line (around 500 characters). Multiple responses in the same line is also supported and will be picked at random based on the amount of responses saved for a trigger.
Triggers are searched by closest matches so single words or short triggers work better, but words can be searched within longer triggers:  
!teach This is a trigger | And this is a response!  
!learn Hey There!|Hey to you too! ;)
!teach Trigger | Response 1 | Response 2 | Oh My

To see how many responses match a phrase, use the !find command followed by the phrase:  
!find Joe  
!find Trixar_za is God

To make Alia forget a learned response use the !forget command followed by the phrase:  
!forget Joe  
!forget Trixar_za is dumb

To see how many responses Alia has learned so far you can use the !responses command:  
!responses

You can also teach Alia to respond with an action instead of a message by prefixing plus (+) to the response:  
!teach I Love you!|+hugs #nick

For a complete list on how to use Alia, please see docs/README for the original Pyborg documentation.

How to use
----------

To use Alia, just run python pyborg-irc.py to generate the cfg files. Press Ctrl+C to stop pyborg-irc.py.
Modify pyborg-irc.cfg and pyborg.cfg to suit your needs and then use ./alia to start the bot silently.
Now allow her to idle in a busy channel so she can learn some basic responses. That's it. You're done. Enjoy!