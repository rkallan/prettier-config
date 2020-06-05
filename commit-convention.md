# Commit Convention by R.Kalla

<hr>
<hr>

<br><br><br>

Every commit made _directly_ to the `master` branch must follow the below convention. Based on commits in the `master` branch release tools will generate changelog entries for the current release.

## Convention

Commit message template:

```
Type: A short sentence about the commit. Closes #XXX.

Optional description.

NOTE: Special note to be marked in the changelog.

BREAKING CHANGE: If any breaking changes were done, they need to be listed here.
BREAKING CHANGE: Another breaking change if needed. Closes #YYY.
```

Accepted commit types:

<table>
<thead>
	<tr>
		<th>Type</th>
		<th>Release</th>
		<th>Description</th>
		<th>Changelog</th>
	</tr>
</thead>
<tbody>
	<tr>
		<td>Feature</td>
		<td><code>minor</code></td>
		<td>A new feature.</td>
		<td>Visible</td>
	</tr>
	<tr>
		<td>Fix</td>
		<td><code>patch</code></td>
		<td>A bug fix. Should also be used for enhancements if they do not introduce new features at the same time.</td>
		<td>Visible</td>
	</tr>
	<tr>
		<td>Other</td>
		<td><code>patch</code></td>
		<td>An enhancement – when it is neither a bug fix nor a feature. For example – public API refactoring. Use it also if you do not want to admit that it was a bug ;).</td>
		<td>Visible</td>
	</tr>
	<tr>
		<td>Code style</td>
		<td><code>patch</code></td>
		<td>Our beloved code style improvements (used in the broad meaning of general code quality).</td>
		<td>Hidden</td>
	</tr>
	<tr>
		<td>Docs</td>
		<td><code>patch</code></td>
		<td>Updated documentation.</td>
		<td>Hidden</td>
	</tr>
	<tr>
		<td>Internal</td>
		<td><code>patch</code></td>
		<td>Other kinds of internal changes.</td>
		<td>Hidden</td>
	</tr>
	<tr>
		<td>Tests</td>
		<td><code>patch</code></td>
		<td>Changes in test files.</td>
		<td>Hidden</td>
	</tr>
	<tr>
		<td>Revert</td>
		<td><code>patch</code></td>
		<td>Revert of some commit.</td>
		<td>Hidden</td>
	</tr>
	<tr>
		<td>Release</td>
		<td><code>patch</code></td>
		<td>A special type of commit used by the release tools.</td>
		<td>Hidden</td>
	</tr>
</tbody>
</table>

Each commit can contain additional notes which will be inserted to the changelog:

<table>
<thead>
	<tr>
		<th>Type</th>
		<th>Is backward compatible?</th>
	</tr>
</thead>
<tbody>
	<tr>
		<td><code>NOTE</code></td>
		<td>Yes</td>
	</tr>
	<tr>
		<td><code>BREAKING CHANGES</code> or <code>BREAKING CHANGE</code></td>
		<td>No</td>
	</tr>
</tbody>
</table>

If any visible change contains the `BREAKING CHANGE` note, the next release will be marked as `major` automatically.

### Example commits

A new feature without any breaking changes.

```
Feature: Added support for RTL languages. Closes #1.

RTL content will now be rendered correctly.

NOTE: Make sure to set `config.contentDirection` correctly.
```

A bug fix for an existing feature (closes two tickets):

```
Fix: The editor will be great again. Closes #3. Closes #4.
```

Commit with updated the documentation:

```
Docs: Updated the README.
```

Commit which provides / changes the tests:

```
Tests: Introduced missing tests. Closes #5.
```

An enhancement which is not backward compatible. Public API has been changed:

```
Other: Extracted `utils.moo()` to a separate package. Closes #9.

BREAKING CHANGE: The `util.moo()` method is now available in the `moo` packages. See #9.
```

For the commits above the changelog will look like this:

```md
```
