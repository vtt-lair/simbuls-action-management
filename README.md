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

![action hud](https://github.com/vtt-lair/simbuls-action-management/assets/33215552/e16d3e86-27e0-48d7-87ba-4c825edb23f4)

#### `Token` Methods

- `setActionUsed(actionType, overrideCount = undefined)`: Sets the provided action type as used for this token and will update the management HUD accordingly.
  - `actionType` {String}: valid values are `action`, `bonus`, and `reaction`. Indicates which action type to modify uses for.
  - `overrideCount` {Number = `undefined`}: optionally sets how many times this action has been used. If set to `0`, restores the action as unsued for combat HUD display.

  - `return value` {Object | `false`}: Current set of used actions and their counts, or `false` if any part of the update failed -- typically due to incorrect action type string.

[Action Mgmt HUD DEMO](https://github.com/vtt-lair/simbuls-action-management/assets/33215552/bf1e5410-3f4f-4725-ae70-e6186eabd434)

