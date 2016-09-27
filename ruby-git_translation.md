## 主なオブジェクト
## Major Objects

**Git::Base** - `Git.open`または` Git.clone`から返されるオブジェクト。ほとんどの主要なアクションは、このオブジェクトから呼び出されます。
> **Git::Base** - The object returned from a `Git.open` or `Git.clone`. Most major actions are called from this object.

**Git::Object** - ベースオブジェクトは、あなたのツリーや、ブロブ、コミットオブジェクトのために、 `@git.gtree`や` @git.object`の呼び出しによって返されます。`Git::AbstractObject` は、これらすべてのオブジェクトのために共通した呼び出しのほとんどを持っています。
> **Git::Object** - The base object for your tree, blob and commit objects, returned from `@git.gtree` or `@git.object` calls.  the `Git::AbstractObject` will have most of the calls in common for all those objects.

 **Git::Diff** - `@git.diff`コマンドから返ります。
 あなたはファイルのパッチおよび挿入/削除ごとの統計情報を取得することができ、そこからDiffFile`オブジェクト：それは `Gitの::差分を返し可算です。また、直接のGit :: Diffのオブジェクトから合計の統計情報を取得することができます。
> **Git::Diff** - returns from a `@git.diff` command.  It is an Enumerable that returns `Git::Diff:DiffFile` objects from which you can get per file patches and insertion/deletion statistics.  You can also get total statistics from the Git::Diff object directly.

** Gitリポジトリ::ステータス** - `@のgit.status`コマンドから戻ります。それは返す可算であります
`Gitは：ステータス:: StatusFile`は、作業中のファイルが含まれgitの内の各オブジェクトのためのオブジェクト
インデックス内やリポジトリ内のディレクトリ、。追跡されていないと変更されたファイルを決定するために、コマンドラインで「Gitのステータスを 'を実行に似ています。
> **Git::Status** - returns from a `@git.status` command.  It is an Enumerable that returns
`Git:Status::StatusFile` objects for each object in git, which includes files in the working
directory, in the index and in the repository.  Similar to running 'git status' on the command line to determine untracked and changed files.

** Gitリポジトリ::支店** - `Gitリポジトリを保持する列挙オブジェクト::支店objects`。あなたは自分のローカルまたはリモートブランチにフィルタリングすることに.localのか.remoteを呼び出すことができます。
> **Git::Branches** - Enumerable object that holds `Git::Branch objects`.  You can call .local or .remote on it to filter to just your local or remote branches.

** ** Gitリポジトリ::リモート - このリポジトリによって追跡されたリモートリポジトリを参照します。
> **Git::Remote**- A reference to a remote repository that is tracked by this repository.

** Gitリポジトリ::ログイン** - :: object`ログイン `Gitリポジトリ上のメソッドを使用して構築することができますログクエリを包含し、すべての` Gitリポジトリ::オブジェクト:: Commit`オブジェクトを、参照する列挙オブジェクト、
以下のように：
> **Git::Log** - An Enumerable object that references all the `Git::Object::Commit` objects that encompass your log query, which can be constructed through methods on the `Git::Log object`,
like:

 > `@git.log(20).object("some_file").since("2 weeks ago").between('v2.6', 'v2.7').each { |commit| [block] }`
