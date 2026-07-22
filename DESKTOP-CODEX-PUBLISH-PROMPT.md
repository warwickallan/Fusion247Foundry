# Desktop Codex publication instruction — migration tranche 1

You have confirmed write access to `warwickallan/Fusion247Foundry`.

Use the attached/unzipped `Fusion247Foundry-migration-tranche-1` directory.

## Authority

Warwick approved the ClickUp Foundry → Git Foundry migration.
The repository must remain public.
Do not create another Foundry repository.
Do not merge.

## Actions

1. Read current `main` and verify the existing repository state.
2. Create branch:
   `migration/clickup-foundry-v1`
3. Preserve the existing large root `README.md` exactly at:
   `archive/bootstrap/2026-07-11-original-foundry-build-plan.md`
4. Apply the tranche-1 directory contents at repository root.
5. Do not overwrite any unrelated existing file without first reconciling it.
6. Commit with:
   `chore(foundry): stage ClickUp migration handbook and inventory`
7. Push the branch.
8. Open one draft PR into `main` titled:
   `chore: migrate ClickUp Foundry into Git`
9. State in the PR:
   - migration is incomplete and must not merge;
   - handbook and destination scaffold are staged;
   - IDEA page bodies, tasks, comments and attachments remain for later commits;
   - Fable's informal pages are authored reviews and must be preserved;
   - repository remains public by Warwick's explicit authority.
10. Report branch, commit SHA, changed paths and draft PR URL.

Do not create GitHub issues yet. They are created only after the migrated idea
records have been reconciled against the ClickUp Current State pages.
