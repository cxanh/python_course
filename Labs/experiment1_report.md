# 实验一 Git和Markdown基础

班级： 22物联1

学号： B20220305117

姓名： 蔡轩

Github地址：<https://github.com/cxanh/python_course>

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

### Level 6 相对引用
动机
- 在 Level 6 中，理解相对引用是很重要的，因为它允许开发者更灵活地导航提交历史。相对引用可以帮助开发者方便地指定相对于某个提交的其他提交，特别是在需要快速访问上一个版本或最近的变更时。

使用的 git 命令

        git checkout bugFix^
git 命令的解释
- git checkout bugFix^：这个命令用于检出 bugFix 分支的上一个提交。符号 ^ 表示“父提交”，即 bugFix 分支当前指向的提交的前一个提交。在执行此命令后，HEAD 将指向 bugFix 分支的父提交，而不是分支的最新状态。通过使用相对引用，可以轻松访问某个提交的历史状态，这在查看变更、调试或撤销某些操作时非常有用。相对引用的使用使得提交导航更加灵活和方便。
### Level 7 相对引用2
动机
- 在 Level 7 中，理解如何使用相对引用来创建和移动分支是非常重要的。这可以帮助开发者灵活地管理提交历史，尤其是在需要重置某个分支到较早的提交时。相对引用的使用使得版本控制变得更加灵活，能够更好地应对代码变更和修复。

使用的 git 命令

        git branch -f main C6
        git checkout HEAD~1
        git branch -f bugFix HEAD~1
git 命令的解释
- git branch -f main C6：这个命令强制将 main 分支指向提交 C6。-f 选项表示强制更新，即使 main 分支已经指向其他提交。此操作会重置 main 分支的历史，使其指向指定的提交。

- git checkout HEAD~1：这个命令用于切换到当前提交的前一个提交（HEAD 的父提交）。~1 表示向后移动一个提交。这允许开发者查看和使用该提交的状态。

- git branch -f bugFix HEAD~1 ：这个命令强制将 bugFix 分支指向当前提交的父提交（即 HEAD~1）。同样，-f 选项表示强制更新，意味着 bugFix 分支将被重置为这个较早的提交。

### Level 8 撤销变更
动机
- 理解如何撤销变更是非常重要的，尤其是在代码开发过程中需要处理错误或不必要的提交时。使用不同的命令（如 git reset 和 git revert）可以根据需求以不同的方式撤销变更，帮助开发者有效管理版本历史。

使用的 git 命令

        git reset HEAD~1
        git checkout pushed
        git revert HEAD
git 命令的解释
- git reset HEAD~1：这个命令用于将当前分支重置到上一个提交（HEAD~1）。这意味着最近的提交将被“撤销”，并且更改将被移回到暂存区。需要注意的是，使用 git reset 撤销提交会改变提交历史，可能会影响与其他开发者的协作。

- git checkout pushed：这个命令用于切换到名为 pushed 的分支，以便在该分支上进行操作。

- git revert HEAD：这个命令用于创建一个新的提交，以撤销当前 HEAD 所指向的提交的所有更改。与 git reset 不同，git revert 保留了提交历史，通过添加一个新的提交来反映撤销操作。这使得代码的历史记录保持一致，适合与其他人协作的场景。


## 远程仓库
### Level 1 git clone
动机
- git clone 是获取远程项目的基础命令。它允许开发者从远程仓库复制完整的项目到本地，从而能够在本地环境中进行开发、修改和版本管理。git clone 是团队协作开发和远程代码共享的起点。

使用的 git 命令

        git clone 
git 命令的解释
- git clone：此命令用于从指定的远程仓库（复制整个项目到本地工作环境。它不仅下载了项目的源代码，还复制了该项目的提交历史、分支等完整信息。此外，git clone 还自动设置了对该远程仓库的引用，通常命名为 origin，方便后续的提交、推送和拉取操作。

### Level 2 远程分支
动机
- 在远程仓库关卡 Level 2 中，了解如何操作远程分支能够帮助开发者轻松地查看和合并来自其他团队成员的更改，确保代码的同步和一致性。掌握远程分支的操作可以提高团队协作的效率。

使用的 git 命令

        git commit
        git checkout o/main
        git commit
git 命令的解释
- git commit：此命令用于将当前工作区的更改提交到本地分支。每次提交都会创建一个新的快照，记录代码的状态和变更，这是管理版本历史的基本操作。

- git checkout o/main：这个命令用于切换到远程分支 o/main，其中 o 是远程仓库的默认前缀，表示该分支来自远程仓库。通过切换到远程分支，开发者可以查看该分支的最新状态，进行代码审查或测试。

- git commit：在切换到远程分支后，再次执行 git commit 可能是为了将本地的更改合并到当前分支。这意味着开发者在查看或使用远程分支的代码后，对其进行了一些修改，并将这些修改提交到该分支。

### Level 3 git Fetch
动机
- 在远程仓库关卡 Level 3 中，了解 git fetch 的使用可以帮助开发者从远程仓库获取最新的更新，而不会自动将这些更新合并到本地分支。通过 git fetch，开发者能够先审查远程分支的变更，再决定是否将其合并到本地分支。这有助于保持本地代码的稳定性和可控性。

使用的 git 命令

        git fetch
git 命令的解释
- git fetch：此命令用于从远程仓库获取更新。git fetch 不会自动将这些更改合并到本地分支，而是将远程分支的状态更新到本地。开发者可以在执行 git fetch 后，查看远程仓库中的最新提交，决定是否要合并这些更改到本地分支。相比于 git pull，git fetch 提供了更大的灵活性，因为它不会直接影响本地代码。

### Level 4 git pull
动机
- 在远程仓库关卡 Level 4 中，了解 git pull 的使用非常关键，因为它结合了 git fetch 和 git merge 的功能。通过 git pull，开发者可以从远程仓库获取最新的更改并自动将其合并到当前的本地分支，这有助于保持本地代码与远程代码的同步，便于团队协作和版本管理。

使用的 git 命令

        git pull
git 命令的解释
- git pull：此命令用于从远程仓库获取最新的更改，并自动将这些更改合并到当前所在的本地分支。它实际上是执行了 git fetch，然后紧接着执行 git merge，因此开发者无需手动分两步完成获取和合并的过程。执行 git pull 后，如果远程分支有新的提交，它们会被合并到当前分支的最新状态中。

### Level 5 模拟团队合作
动机
- 通过掌握如何从远程仓库克隆项目、进行本地更改并与团队成员的更新保持同步，开发者可以高效地参与协作开发，确保项目的持续进展和稳定性。

使用的 git 命令

        git clone 
        git fakeTeamwork 2
        git commit
        git pull
git 命令的解释
- git clone：此命令用于从指定的远程仓库复制整个项目到本地。它创建了本地副本，并配置了远程连接，开发者可以在本地环境中查看和修改代码。

- git fakeTeamwork 2：此命令是一个模拟团队合作的自定义命令，假设它表示进行某种协作或变更的过程。在实际操作中，模拟队友推送了 2 个提交记录到远程仓库的分支。

- git commit：此命令用于将当前工作区的更改提交到本地分支。每次提交都会记录一份快照，反映出本地的变更状态，为后续的版本管理提供依据。

- git pull：此命令用于从远程仓库获取最新的更改，并自动将其合并到当前的本地分支。这意味着在团队合作过程中，开发者可以迅速同步其他团队成员的修改，确保本地代码与远程仓库的一致性。

### Level 6 git push
动机
- 通过 git push，开发者可以将本地分支的提交上传到远程仓库，使得其他团队成员能够访问到最新的更改。这一过程确保了代码的共享和协作，促进了团队的有效沟通和项目的持续进展。

使用的 git 命令

        git commit
        git commit
        git push
git 命令的解释
- git commit：此命令用于将当前工作区的更改提交到本地分支。每次提交都会生成一个新的快照，记录代码的状态和修改，形成版本历史。

- git commit（再次执行）：再次提交更改，记录后续的修改。这通常发生在开发者进行多次更改后，希望将这些更改分开记录。

- git push：此命令用于将本地分支的提交推送到远程仓库。通过执行 git push，开发者可以将本地的更改上传到远程分支，使其他团队成员能够获取到最新的代码和修改。这一步是团队合作中不可或缺的一部分，确保所有人都在同一基础上进行开发。

### Level 7 偏离的提交历史
动机
- 在远程仓库关卡 Level 7 中，理解如何处理偏离的提交历史尤为重要。通过使用 git pull --rebase，开发者可以将本地的提交应用到远程分支的最新状态上，避免产生额外的合并提交，从而保持提交历史的线性。这有助于提高代码历史的可读性，简化版本管理。

使用的 git 命令

        git clone 
        git fakeTeamwork
        git commit
        git pull --rebase
        git push
git 命令的解释
- git clone：此命令用于从远程仓库复制项目到本地，为后续开发创建一个完整的副本，并配置与远程仓库的连接。

- git fakeTeamwork：此命令假设为一个模拟团队合作的自定义命令，可能涉及多个开发者对代码的修改或功能的添加。在实际场景中，这可能代表在本地进行的多次变更。

- git commit：此命令用于将当前工作区的更改提交到本地分支，生成一个新的快照以记录变更历史。

- git pull --rebase：此命令用于从远程仓库获取最新的更改，并将本地的提交应用到这些更改之后。通过使用 --rebase 选项，开发者能够避免生成额外的合并提交，保持提交历史的整洁和线性。这在处理多个开发者共同作业时尤其有用，可以使项目的版本历史更加清晰。

- git push：此命令用于将本地分支的提交推送到远程仓库，确保其他团队成员可以访问到最新的代码和修改。通过这一过程，开发者将本地的变更共享给团队，实现协作开发。
### Level 8 Locked Main
动机
- 通过使用 git reset --hard 命令，开发者可以将本地分支强制重置为远程主分支的状态。这在需要恢复到主分支的稳定版本时尤其有用，确保本地开发环境的一致性。新建一个分支feature, 推送到远程服务器. 然后reset你的main分支和远程服务器保持一致, 否则下次pull并且他人的提交和冲突的时候就会有问题.

使用的 git 命令

        git reset --hard origin/main
        git checkout -b feature
        git push origin feature
git 命令的解释
- git reset --hard origin/main：此命令用于将当前分支强制重置为远程主分支的最新状态。--hard 选项表示所有未提交的更改将被丢弃，工作目录将被重置为与 origin/main 完全一致。这通常用于清理不必要的本地变更，确保回到主分支的稳定版本。

- git checkout -b feature：此命令用于创建并切换到一个名为 feature 的新分支。可以在此分支上进行新的功能开发，而不影响主分支的稳定性。

- git push origin feature：此命令用于将新创建的 feature 分支推送到远程仓库。通过这一过程，可以将功能开发与团队共享，使其他成员能够访问和协作开发。
## 实验总结

总结一下这次实验你学习和使用到的知识，例如：编程工具的使用、数据结构、程序语言的语法、算法、编程技巧、编程思想。
  
 - 在此次实验学习中，我深入掌握了 Git 作为版本控制工具的使用，包括远程仓库操作和分支管理。通过学习命令如 clone、commit、push 和 pull，理解了如何高效地在团队环境中管理代码，处理远程分支和同步更改。此外，学习了如何使用 pull --rebase 命令保持提交历史的线性，掌握了版本回滚和错误恢复的技巧，如 reset --hard。我增强了对命令行工具的熟练度，并提高了在团队协作中确保代码稳定性的能力，了解了分支策略和代码管理的重要性。
 - 我还学会了如何在github上编辑md文件，对git仓库工具也是驾轻就熟。
 - 总体而言，这些知识和技能为未来的开发工作打下了坚实的基础，有助于更有效地参与团队项目。
