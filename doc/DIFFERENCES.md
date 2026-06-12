## Differences from Hiroyuki Sato's scripts

### Join Reasonably.jsx

In the [original script](http://shspage.com/aijs/en/#join_reasonably), the "Close paths" (`conf.close`) only worked when the "Join all paths" option was also set (when `conf.ignore_if_further_than` was disabled), whereas in the current script they can be used together.

In the original script, unsetting the "Close paths" option forced all resulting paths to be open, whereas in the current script any endpoints that are less than "Join threshold" apart (as long as it is set) will joined, which may produce closed paths even without the "Close paths" setting.

<table>
	<tr>
		<th>Setting</th>
		<th>Current script</th>
		<th>Original script</th>
	</tr>
	<tr>
		<td>
			Join threshold: <i>disabled</i><br />
			Join all paths: 🗹<br />
			Close paths: 🗹
		</td>
		<td>Single closed path</td>
		<td>Single closed path</td>
	</tr>
	<tr>
		<td>
			Join threshold: <i>set</i><br />
			Join all paths: ☐<br />
			Close paths: 🗹
		</td>
		<td>One or more paths, all <mark>closed</mark></td>
		<td>One or more paths, all <mark>open</mark>;<br />"Close paths" ignored</td>
	</tr>
	<tr>
		<td>
			Join threshold: <i>disabled</i><br />
			Join all paths: 🗹<br />
			Close paths: ☐
		</td>
		<td>Single open path</td>
		<td>Single open path</td>
	</tr>
	<tr>
		<td>
			Join threshold: <i>set</i><br />
			Join all paths: ☐<br />
			Close paths: ☐
		</td>
		<td>One or more paths,<br /><mark>may be closed</mark> if<br />path joined to itself</td>
		<td>One or more paths, <mark>all open</mark>;<br />never joined to itself even<br />when within threshold</td>
	</tr>
</table>

The original script provides additional configurable settings, `conf.hanLen` and `conf.dontAddRevHan`. These are still present but can only be configured by modifying the script file itself. More information on these settings can be found in the [original description](http://shspage.com/aijs/en/#join_reasonably).
