(rr-vcs-git-commit)=
# The `git commit` Command

Every time you 'add' changes (new files or existing files with some changes) and 'commit' those in your Git repository, you create a version of your project that is stored in your project history and can be accessed any time.

To commit changes with a meaning statement about changes made in a version, use `git commit` with a `-m` (m for message) flag:

```
git commit -m 'helpful statement about the change here'
```

You can see a log of your previous commits using

```
git log
```

In the log report on your terminal, you will see that each version is automatically tagged with a unique string of numbers and letters, called an SHA. You can identify, access and compare different versions by using their corresponding SHA. 这里是在Git日志中的一个承诺示例： SHA在第一行，除了这个SHA。 日志还包含关于变更的日期、时间和作者以及提交消息的信息("小打字")。

```
commit 0346c937d0c451f6c622c5800a46f9e9e1c2b035
Author: Malvika Sharan <some@email.com>
Date:   Wed May 6 18:22:40 2020 +0100

    minor typo fix

```

(rr-vcs-commit-messages)=
## More on the Commit Messages

As you work on your project, you will make more and more commits. Without any other information, it can be hard to remember which version of your project is in which. Storing past versions is useless if you can not understand them, and figuring out what they contain by inspecting the code is frustrating and takes valuable time.

When you commit, you have the chance to write a commit message describing what the commit is and what it does, and you should always, *always,* **_always_** do so. A commit message gets attached to the commit, so if you look back at it (for example, via `git log`), it will show up. Creating insightful and descriptive commit messages is one of the best things you can do to get the most out of version control. It lets people (and your future self when you have long since forgotten what you were doing and why) quickly understand what updates a commit contains without having to carefully read code and waste time figuring it out. Good commit messages improve your code quality by drastically reducing wrong assumptions by people on why certain changes were made.

When you commit via `git commit` without the `-m` or `--message` option, a field appears (either within the terminal or in a text editor) where a commit message can be written. You can write a meaningful statement and save (and close if writing the message via text editor). You can set your preferred editor as the default by running a statement like this:

```
git config --global core.editor "your_preferred_editor"
```

To avoid writing this commit message in an editor, you can use the command `git commit -m "your message here"`, as discussed earlier.

(rr-vcs-commit-messages-practice)=
### Good practice

The number one rule is: **make it meaningful**. 像“修复bug”这样的提交消息让人完全了解这意味着什么(再次)。 这个人很可能在今后几个月里成为你，因为你们忘记了你们当时的所作所为）。 这最终会浪费您或其他人的时间去找出错误的原因。 This can end up wasting your or others time figuring out what the bug was, what changes were actually made, and how a bug was fixed. As such, a good commit message should *explain what you did, why you did it, and what is impacted by the changes*. As with comments, you should describe what the code is "doing" rather than the code itself. For example, it is not obvious what "Change N_sim to 10" actually does, but "Change number of simulations run by the program to 10" is clear.

**Summarise the changes your commit contains**. This should be written in the first line (in 50 characters maximum), then leave a blank line before you continue with the description or body of the message. The first line is the shortened version that appears as a summary when you use the command:

```
git log
```

This makes it much easier to quickly search through a large number of commits. 在这些消息中使用 **也是一种很好的做法。 ** 使用当前必须的紧张状态。 For example, instead of "I added tests for" or "Adding tests for", use "Add tests for".

Here is a good example of a commit message structure:

```
Short (50 chars. or less) summary of changes

More detailed explanatory text, if necessary. 把它包裹到
大约72个字符。 Wrap it to
about 72 characters or so. In some contexts, the first
line is treated as the subject of an email and the rest of
the text as the body. The blank line separating the
summary from the body is critical (unless you omit the body
entirely); tools like rebase can get confused if you run
the two together.

Further paragraphs come after blank lines.

  - 子点可以用来制造子弹，也可以用

  - 通常情况下，子弹是用连字符或星号。 之前有一个空格, 空白行在
    之间, 但在此处的约定有差异
```
(rr-vcs-commit-summary)=
## Git commit: Summary

By committing your changes throughout the development of your project in meaningful units with descriptive and clear commit messages, you can create an easily understandable history. This will help you and others to understand the progress of your work. Furthermore, as the next section will demonstrate, it will also make it easy to view past versions of your history or revert changes you have made.
