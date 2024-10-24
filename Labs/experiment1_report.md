# 实验一 Git和Markdown基础

班级： 22物联1

学号： 202302200000

姓名： 张三

Github地址：<https://github.com/yourusername/python_course>

---

## 实验目的

1. Git基础，使用Git进行版本控制
2. Markdown基础，使用Markdown进行文档编辑
3. vscode的基本使用

## 实验环境

1. Git
2. VSCode
3. VSCode插件

## 实验过程记录

Git实验过程的记录请参考[Learning Git Branch Tutorial](https://github.com/zhoujing204/python_course/blob/main/Labs/LearningGitBranch-Tutorial.md)，请记录下每个git小实验的:

- 动机: 为什么要使用这个git命令，或者这个git命令的作用是什么？

- 使用的git命令：使用markdown代码块的形式记录下你使用的git命令，例如：

  ```shell
  git branch
  ```
- git命令的解释：使用自然语言解释你使用的git命令

### Level 1 git commit
- 动机：
  在 Level 1 中，我们的目标是了解如何提交更改。git commit 是 Git 中最核心的命令之一，它将文件的修改保存到仓库历史中。每次提交都会创建一个新的快照，记录当前的文件状态。通过 git commit，开发者可以逐步记录和保存代码的开发过程，并为后续的版本控制提供基础。

- 使用的 git 命令：
  
          git commit
          git commit
- git 命令的解释：
  git commit 该命令用于将暂存区的更改提交到本地仓库历史中,只需两次即可达到目标

### Level 2 git branch
动机
- 在 Level 2 中，我们的目标是理解如何创建新分支以及在分支之间切换。这在 Git 工作流中至关重要，因为它使得开发者能够在不同的分支上独立工作而不干扰到主分支的代码。这也为代码审查和测试提供了灵活性，确保主分支保持稳定。

使用的 git 命令

        git branch bugFix
        git checkout bugFix
git 命令的解释
- git branch bugFix：这个命令用于创建一个名为 bugFix 的新分支。此时，虽然分支已经创建，但仍然在原来的分支上。

- git checkout bugFix：这个命令用于切换到刚刚创建的 bugFix 分支。在执行此命令后，所有的后续更改将会在 bugFix 分支上进行，而不会影响到原来的分支。这种切换允许开发者在不同的功能或任务之间轻松切换。

### Level 3 git merge
动机
-在 Level 3 中，了解如何使用 git merge 将一个分支的更改合并到主分支是至关重要的。这使得开发者能够将独立开发的功能或修复整合到主代码库中，从而保持项目的连贯性和更新。

使用的 git 命令

      git checkout -b bugFix
      git commit
      git checkout main
      git commit
      git merge bugFix

git 命令的解释

git checkout -b bugFix：这个命令用于创建并切换到名为 bugFix 的新分支。-b 选项表示创建新分支并立即切换到该分支，使得开发者能够在这个新分支上进行工作。

git commit -m：在 bugFix 分支上，开发者提交。

git checkout main：这个命令用于切换回主分支（main）。在合并操作之前，需要确保他们在目标分支上。

git commit：在主分支上进行的提交，表明准备合并来自 bugFix 分支的更改。可以帮助记录合并前的状态。

git merge bugFix：这个命令将 bugFix 分支的更改合并到当前分支（main）。如果没有冲突，Git 会自动完成合并，更新主分支以包含来自 bugFix 的所有更改。

### Level 4 git ReBase
动机
-在 Level 4 中，使用 git rebase 可以帮助开发者将一个分支的更改整合到另一个分支的基础上，保持代码的整洁和历史的线性。这在代码审查和版本管理中是非常重要的，因为它使得历史记录更易读，便于理解项目的演变。

使用的 git 命令

        git checkout -b bugFix
        git commit
        git checkout main
        git commit
        git checkout bugFix
        git rebase main

git 命令的解释
- git checkout -b bugFix：创建并切换到名为 bugFix 的新分支，开始在此分支上进行开发。

- git commit：在 bugFix 分支上提交当前的更改，记录提交到历史中。

- git checkout main：切换回主分支 main，准备进行下一步操作。

- git commit：在 main 分支上提交当前的更改，更新主分支的状态。

- git checkout bugFix：切换回 bugFix 分支，以便进行变基操作。

- git rebase main：将 bugFix 分支的更改基于 main 分支的最新状态。这意味着 bugFix 上的提交将被重新应用在 main 上的最新提交之后，保持提交历史的线性和清晰。

### Level 5 分离HEAD
动机
- 在 Level 5 中，理解如何处理分离的 HEAD 状态是非常重要的。分离 HEAD 指的是当前检出的是某个具体的提交而不是分支，这意味着任何在此状态下的提交不会直接与任何分支关联。这在需要查看或测试某个特定提交的状态时非常有用，但要小心，因为如果不正确处理，可能会丢失未关联的提交。

使用的 git 命令

        git checkout C4
        
git 命令的解释
- git checkout C4：这个命令用于检出（checkout）一个具体的提交（C4）。在执行此命令后，HEAD 指向了提交 C4，而不是任何一个分支。这就导致了分离 HEAD 的状态。在此状态下，查看 C4 版本的代码，甚至在此基础上进行更改和提交，但这些提交不会被记录到任何分支上。

## 实验总结

总结一下这次实验你学习和使用到的知识，例如：编程工具的使用、数据结构、程序语言的语法、算法、编程技巧、编程思想。
