---
title: Abrir soluções do controle do código-fonte | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- opening solutions
- solutions [SQL Server Management Studio], opening
ms.assetid: a96a1f0d-0183-4587-a3b0-4598309cbdd2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 808a4851bcc1f51690b2ba924a859bcccf9a6adb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582596"
---
# <a name="open-solutions-from-source-control"></a><span data-ttu-id="71b96-102">Abrir soluções no controle do código-fonte</span><span class="sxs-lookup"><span data-stu-id="71b96-102">Open Solutions from Source Control</span></span>
  <span data-ttu-id="71b96-103">Você pode usar o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para abrir soluções diretamente do controle do código-fonte.</span><span class="sxs-lookup"><span data-stu-id="71b96-103">You can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to open solutions directly from source control.</span></span> <span data-ttu-id="71b96-104">Quando você faz isso, o ambiente do Studio cria uma cópia da última versão dos arquivos da solução no local que você especifica.</span><span class="sxs-lookup"><span data-stu-id="71b96-104">When you do this, the Studio environment creates a copy of the latest version of the solution files at the location you specify.</span></span>  
  
 <span data-ttu-id="71b96-105">Se não existir uma cópia local da solução em seu disco local, abra o projeto a partir do controle do código-fonte antes de poder usar o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para fazer o check-out da solução ou recuperar os arquivos da solução.</span><span class="sxs-lookup"><span data-stu-id="71b96-105">If a local copy of the solution does not exist on your local disk, you must open the project from source control before you can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to check out the solution or retrieve solution files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="71b96-106">Se você já tiver uma cópia local da solução que você está abrindo a partir do controle do código-fonte, será solicitado a substituir a cópia local.</span><span class="sxs-lookup"><span data-stu-id="71b96-106">If you already have a local copy of the solution you are opening from source control, you are prompted to overwrite the local copy.</span></span>  
  
### <a name="to-open-a-solution-from-source-control"></a><span data-ttu-id="71b96-107">Para abrir uma solução no controle do código-fonte</span><span class="sxs-lookup"><span data-stu-id="71b96-107">To open a solution from source control</span></span>  
  
1.  <span data-ttu-id="71b96-108">No menu **arquivo** , aponte para **controle do código-fonte**e clique em **Abrir do controle do código-fonte**.</span><span class="sxs-lookup"><span data-stu-id="71b96-108">On the **File** menu, point to **Source Control**, and click **Open From Source Control**.</span></span>  
  
2.  <span data-ttu-id="71b96-109">Se solicitado, faça logon no [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe.</span><span class="sxs-lookup"><span data-stu-id="71b96-109">If prompted, log on to [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe.</span></span>  
  
3.  <span data-ttu-id="71b96-110">Na caixa de diálogo **criar projeto local do SourceSafe** , selecione a pasta que contém a solução que você deseja abrir e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="71b96-110">In the **Create local project from SourceSafe** dialog box, select the folder that contains the solution you want to open, and click **OK**.</span></span>  
  
4.  <span data-ttu-id="71b96-111">Se uma pasta de trabalho para a solução já existir em sua unidade de disco local, a caixa **criar um novo projeto na pasta** será alterada para identificar o diretório local.</span><span class="sxs-lookup"><span data-stu-id="71b96-111">If a working folder for the solution already exists on your local disk drive, the **Create a new project in the folder** box changes to identify the local directory.</span></span> <span data-ttu-id="71b96-112">Se não houver uma pasta de trabalho para a solução, você poderá digitar ou procurar o diretório local em que a solução deve ser aberta.</span><span class="sxs-lookup"><span data-stu-id="71b96-112">If no working folder for the solution exists, you can type or browse to the local directory in which the solution should be opened.</span></span>  
  
5.  <span data-ttu-id="71b96-113">Na caixa de diálogo **Abrir solução** , selecione o arquivo de solução e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="71b96-113">In the **Open Solution** dialog box, select the solution file, and click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71b96-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="71b96-114">See Also</span></span>  
 [<span data-ttu-id="71b96-115">Abrir projetos no controle do código-fonte</span><span class="sxs-lookup"><span data-stu-id="71b96-115">Open Projects from Source Control</span></span>](../../2014/database-engine/open-projects-from-source-control.md)  
  
  
