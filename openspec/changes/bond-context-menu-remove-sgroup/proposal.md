## Why

Users cannot find a way to remove an S-group once it is added, while keeping its atoms and bonds (#4677). The Eraser does this when the user clicks the S-group's bracket or data label, but nothing in the menus or the S-Group Properties dialog points to it. The bond context menu already offers **Attach S-Group...** and **Edit S-Group...** (#1996); it should also offer **Remove S-Group**.

## What Changes

- The bond context menu in Molecules mode gets **Remove S-Group**, placed after **Edit S-Group...**.
- It deletes the S-group that contains the bond and keeps its atoms and bonds. It is one undo step.
- It is shown and enabled by the same rules as **Edit S-Group...**: hidden when the bond is in no S-group or in a superatom without a label, disabled when the bond is in more than one S-group or when several bonds are in the menu.
- It is hidden for functional groups and monomers, which have their own items (**Remove Abbreviation**, **Remove Grouping**), and disabled while the monomer creation wizard is open.
- New translation key `components:contextMenu.removeSGroup` in every locale.

Out of scope, left for a follow-up on #4677: changing which atoms belong to an existing S-group, a remove button in the S-Group Properties dialog, and the atom context menu (its S-group items are added by #2347).

## Capabilities

### New Capabilities

<!-- None. -->

### Modified Capabilities

- `templates-and-groups`: adds a requirement for removing an S-group from the bond context menu.

## Impact

- `ketcher-react`: `ContextMenu/menuItems/BondMenuItems.tsx`, new `ContextMenu/hooks/useBondSGroupRemove.ts`, `locales/*/components.json`.
- Uses the existing `fromSgroupDeletion` action. No `ketcher-core` change, no file format change, no public API change.
