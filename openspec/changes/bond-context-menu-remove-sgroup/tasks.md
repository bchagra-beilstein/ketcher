## 1. Remove S-Group item

- [x] 1.1 Add `useBondSGroupRemove` in `ContextMenu/hooks/` with the rules from `useBondSGroupEdit`, hidden for functional groups and monomers
- [x] 1.2 Add **Remove S-Group** after **Edit S-Group...** in `BondMenuItems.tsx`, test id `Remove S-Group-option`
- [x] 1.3 Add `components:contextMenu.removeSGroup` to every locale
- [x] 1.4 Unit tests for the hook: shown, hidden, disabled cases and the removal

## 2. Verification

- [x] 2.1 `ketcher-react` checks pass: lint, types, unit tests
- [x] 2.2 Verify in the app: remove a polymer and a data S-group from a bond, atoms and bonds stay, undo restores each one, no item on a bond in no S-group
