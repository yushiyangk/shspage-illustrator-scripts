## Changelog

### 0.2.0

Changes from original from http://shspage.com/aijs/en/

#### Added

GUI dialog for configuration

#### Changed

- The `conf.ignore_if_further_than` setting is now presented as two separate but linked options: "Join threshold" and "Join all paths"
- Previously, the `conf.close` setting only worked when the `conf.ignore_if_further_than` setting was disabled, whereas now the "Close paths" option can be used when "Join threshold" is unset (which occurs when "Join all paths" is checked).
	- "Join threshold" is set to 0.5 and "Join all paths" is disabled by default, where previously `conf.ignore_if_further_than` was disabled by default
- Previously, setting `conf.close` to `false` forced all resulting paths to be open, whereas now any endpoints that are less than "Join threshold" apart (as long as it is set) will joined, which may produce closed paths even without the "Close paths" setting
	- "Close paths" is disabled by default (thanks to the change in behaviour), where previously `conf.close` was set to `true` by default
- Changed the boundary condition of "Merge anchors" to <= rather than <, such that two anchors that have a distance exactly equal to the "Merge anchors" threshold will now be merged
