# Simbul's Action Management

- Action HUD added to tokens during combat, tracking their Reaction, Action, and Bonus Action (left to right).
  - Positive action cost items will mark the corresponding action as used.
  - Negative action cost items will refund the corresponding action. Ex. Action Surge configured as "-1 Action".
  - Items with usage of "Action" will be interpretted as a Reaction when used on another actor's turn.
- Used actions will reset at the beginning of the combatant's turn.
- Additional control added to the token HUD during combat to manually adjust actions.
- Used actions can optionally be displayed as status effects for easier tracking.
- When the action HUD is visible, clicking on an action icon will consume that action, clicking a used action will restore it for use.
- Note: This management is for display purposes only and will not interfere with item use.

![action-hud](https://user-images.githubusercontent.com/14878515/160882602-3e58868e-9e6e-444b-88b4-5189e647271e.jpg)

#### Added `Token` Methods

- `setActionUsed(actionType, overrideCount = undefined)`: Sets the provided action type as used for this token and will update the management HUD accordingly.
  - `actionType` {String}: valid values are `action`, `bonus`, and `reaction`. Indicates which action type to modify uses for.
  - `overrideCount` {Number = `undefined`}: optionally sets how many times this action has been used. If set to `0`, restores the action as unsued for combat HUD display.

  - `return value` {Object | `false`}: Current set of used actions and their counts, or `false` if any part of the update failed -- typically due to incorrect action type string.

[Action Mgmt HUD DEMO](https://user-images.githubusercontent.com/14878515/131264314-d4017b8a-fa7a-4bf8-8f62-795145441605.mp4)
