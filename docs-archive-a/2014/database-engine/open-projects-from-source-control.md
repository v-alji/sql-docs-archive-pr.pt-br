---
title: Abrir projetos do controle do código-fonte | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- projects [SQL Server Management Studio], opening
- opening projects
ms.assetid: 942f93a3-e264-4ec4-ba72-a28e0509a527
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 944b121516e3782e35e213e165405b0ecceb7456
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582598"
---
# <a name="open-projects-from-source-control"></a><span data-ttu-id="a65a4-102">Abrir projetos no controle do código-fonte</span><span class="sxs-lookup"><span data-stu-id="a65a4-102">Open Projects from Source Control</span></span>
  <span data-ttu-id="a65a4-103">Você pode usar o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para abrir projetos diretamente do controle doe código-fonte.</span><span class="sxs-lookup"><span data-stu-id="a65a4-103">You can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to open projects directly from source control.</span></span> <span data-ttu-id="a65a4-104">Quando você fizer isso, o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] recuperará a versão mais recente do projeto e a copiará em seu disco local.</span><span class="sxs-lookup"><span data-stu-id="a65a4-104">When you do this, [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] retrieves the latest version of the project and copies it to your local disk.</span></span> <span data-ttu-id="a65a4-105">O ambiente do [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] também cria automaticamente uma solução para o projeto.</span><span class="sxs-lookup"><span data-stu-id="a65a4-105">The [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment also creates a solution for the project automatically.</span></span>  
  
 <span data-ttu-id="a65a4-106">Depois de abrir um projeto a partir do controle do código-fonte, você poderá fazer check-out e modificar os arquivos de projeto.</span><span class="sxs-lookup"><span data-stu-id="a65a4-106">After you have opened a project from source control, you can check out and modify the project files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a65a4-107">O procedimento a seguir só deve ser usado uma vez.</span><span class="sxs-lookup"><span data-stu-id="a65a4-107">The following procedure should only be used once.</span></span> <span data-ttu-id="a65a4-108">Depois disso, você deve abrir o projeto como qualquer outro projeto (clicando em **arquivo**, **abrir**e, em seguida, **projeto**).</span><span class="sxs-lookup"><span data-stu-id="a65a4-108">Thereafter, you should open the project like any other project (by clicking **File**, **Open**, and then **Project**).</span></span>  
  
### <a name="to-open-a-project-from-source-control"></a><span data-ttu-id="a65a4-109">Para abrir um projeto no controle do código-fonte</span><span class="sxs-lookup"><span data-stu-id="a65a4-109">To open a project from source control</span></span>  
  
1.  <span data-ttu-id="a65a4-110">No menu **arquivo** , aponte para **controle do código-fonte**e clique em **Abrir do controle do código-fonte**.</span><span class="sxs-lookup"><span data-stu-id="a65a4-110">On the **File** menu, point to **Source Control**, and click **Open From Source Control**.</span></span>  
  
2.  <span data-ttu-id="a65a4-111">Se solicitado, faça logon no [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe.</span><span class="sxs-lookup"><span data-stu-id="a65a4-111">If prompted, log on to [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe.</span></span>  
  
3.  <span data-ttu-id="a65a4-112">Na caixa de diálogo **criar projeto local do SourceSafe** , abra a pasta que contém o projeto a ser aberto.</span><span class="sxs-lookup"><span data-stu-id="a65a4-112">In the **Create local project from SourceSafe** dialog box, open the folder that contains the project to open.</span></span>  
  
4.  <span data-ttu-id="a65a4-113">A caixa **criar um novo projeto na pasta** é alterada para identificar o diretório local no qual o projeto será criado.</span><span class="sxs-lookup"><span data-stu-id="a65a4-113">The **Create a new project in the folder** box changes to identify the local directory in which the project will be created.</span></span> <span data-ttu-id="a65a4-114">Se você quiser colocar o projeto em um diretório diferente, digite o caminho para o diretório ou use o botão **procurar** para localizar o diretório no disco local.</span><span class="sxs-lookup"><span data-stu-id="a65a4-114">If you want to place the project in a different directory, type the path to the directory or use the **Browse** button to locate the directory on your local disk.</span></span>  
  
5.  <span data-ttu-id="a65a4-115">Na **caixa criar um novo projeto na pasta**, verifique se a pasta correta é exibida e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a65a4-115">In the **Create a new project in the folder box**, verify that the correct folder is displayed, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="a65a4-116">Na caixa de diálogo **Abrir solução** , selecione o projeto que você deseja abrir e clique em **abrir**.</span><span class="sxs-lookup"><span data-stu-id="a65a4-116">In the **Open Solution** dialog box, select the project you want to open, and click **Open**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a65a4-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a65a4-117">See Also</span></span>  
 <span data-ttu-id="a65a4-118">[Abrir soluções e projetos do controle do código-fonte](../../2014/database-engine/open-solutions-and-projects-from-source-control.md) </span><span class="sxs-lookup"><span data-stu-id="a65a4-118">[Open Solutions and Projects from Source Control](../../2014/database-engine/open-solutions-and-projects-from-source-control.md) </span></span>  
 [<span data-ttu-id="a65a4-119">Abrir soluções no controle do código-fonte</span><span class="sxs-lookup"><span data-stu-id="a65a4-119">Open Solutions from Source Control</span></span>](../../2014/database-engine/open-solutions-from-source-control.md)  
  
  
