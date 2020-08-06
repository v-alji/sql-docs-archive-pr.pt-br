---
title: Recuperar arquivos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- version control services [SQL Server], file retrieval
- file retrieval [SQL Server]
- retrieving files
ms.assetid: 37b74426-e262-43b2-a81f-79b1fd1a36ec
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ebced9ea69f304344893289140687cd6d511e923
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582104"
---
# <a name="retrieve-files"></a><span data-ttu-id="a42d6-102">Recuperar arquivos</span><span class="sxs-lookup"><span data-stu-id="a42d6-102">Retrieve Files</span></span>
  <span data-ttu-id="a42d6-103">Após abrir um projeto com controle do código-fonte, você pode usar o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para recuperar cópias locais de arquivos do projeto da armazenagem do controle do código-fonte para o diretório local em que o projeto fica armazenado.</span><span class="sxs-lookup"><span data-stu-id="a42d6-103">After you have opened a source-controlled project, you can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to retrieve local copies of project files from the source control store to the local directory in which the project resides.</span></span>  
  
 <span data-ttu-id="a42d6-104">Você pode usar o controle do código-fonte integrado para recuperar arquivos de acordo com um dos modos a seguir:</span><span class="sxs-lookup"><span data-stu-id="a42d6-104">You can use integrated source control to retrieve files in the following ways:</span></span>  
  
-   <span data-ttu-id="a42d6-105">**Obter o comando de versão mais recente (recursivo)**</span><span class="sxs-lookup"><span data-stu-id="a42d6-105">**Get Latest Version (Recursive)** command</span></span>  
  
     <span data-ttu-id="a42d6-106">Recupera a última versão registrada dos arquivos selecionados.</span><span class="sxs-lookup"><span data-stu-id="a42d6-106">Retrieves the latest checked in version of the selected files.</span></span> <span data-ttu-id="a42d6-107">Se uma solução ou um projeto for selecionado, esse comando recuperará a versão mais recente de todos os arquivos da solução e do projeto.</span><span class="sxs-lookup"><span data-stu-id="a42d6-107">If a solution or project is selected, this command retrieves the latest version of all solution and project files.</span></span>  
  
-   <span data-ttu-id="a42d6-108">Comando **Get**</span><span class="sxs-lookup"><span data-stu-id="a42d6-108">**Get** command</span></span>  
  
     <span data-ttu-id="a42d6-109">Exibe a caixa de diálogo **obter** , que pode ser usada para recuperar a versão mais recente de um arquivo selecionado ou para recuperar um subconjunto dos arquivos na solução ou projeto selecionado.</span><span class="sxs-lookup"><span data-stu-id="a42d6-109">Displays the **Get** dialog box, which you can use to retrieve the latest version of a selected file, or to retrieve a subset of the files in the selected solution or project.</span></span>  
  
### <a name="to-retrieve-the-latest-version-of-all-the-files-in-a-project"></a><span data-ttu-id="a42d6-110">Para recuperar a versão mais recente registrada de todos os arquivos em um projeto</span><span class="sxs-lookup"><span data-stu-id="a42d6-110">To retrieve the latest version of all the files in a project</span></span>  
  
1.  <span data-ttu-id="a42d6-111">No Gerenciador de Soluções, selecione o projeto.</span><span class="sxs-lookup"><span data-stu-id="a42d6-111">In Solution Explorer, select the project.</span></span>  
  
2.  <span data-ttu-id="a42d6-112">No menu **arquivo** , aponte para **controle do código-fonte**e clique em **obter versão mais recente (recursivo)**.</span><span class="sxs-lookup"><span data-stu-id="a42d6-112">On the **File** menu, point to **Source Control**, and then click **Get Latest Version (Recursive)**.</span></span>  
  
 <span data-ttu-id="a42d6-113">As versões mais recentes dos arquivos do projeto são recuperadas no local do projeto no disco local.</span><span class="sxs-lookup"><span data-stu-id="a42d6-113">The most recent versions of the files in the project are retrieved to the project location on your local disk.</span></span>  
  
#### <a name="to-retrieve-only-certain-files-in-a-project"></a><span data-ttu-id="a42d6-114">Para recuperar somente determinados arquivos em um projeto</span><span class="sxs-lookup"><span data-stu-id="a42d6-114">To retrieve only certain files in a project</span></span>  
  
1.  <span data-ttu-id="a42d6-115">No Gerenciador de Soluções, selecione o item que você deseja recuperar.</span><span class="sxs-lookup"><span data-stu-id="a42d6-115">In Solution Explorer, select the item you want to retrieve.</span></span>  
  
2.  <span data-ttu-id="a42d6-116">No menu **arquivo** , aponte para **controle do código-fonte**e clique em **obter**.</span><span class="sxs-lookup"><span data-stu-id="a42d6-116">On the **File** menu, point to **Source Control**, and then click **Get**.</span></span>  
  
3.  <span data-ttu-id="a42d6-117">Na caixa de diálogo **obter** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a42d6-117">In the **Get** dialog box, click **OK**.</span></span> <span data-ttu-id="a42d6-118">Como alternativa, se você tiver selecionado uma solução ou um projeto no Gerenciador de Soluções, desmarque as caixas de seleção que aparecem próximas aos itens que não deseja recuperar.</span><span class="sxs-lookup"><span data-stu-id="a42d6-118">Alternatively, if you selected a solution or project in Solution Explorer, clear the check boxes that appear next to the items you do not want to retrieve.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a42d6-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a42d6-119">See Also</span></span>  
 <span data-ttu-id="a42d6-120">[Caixa de diálogo Get &#40;controle do código-fonte&#41;](../../2014/database-engine/get-dialog-box-source-control.md) </span><span class="sxs-lookup"><span data-stu-id="a42d6-120">[Get Dialog Box &#40;Source Control&#41;](../../2014/database-engine/get-dialog-box-source-control.md) </span></span>  
 <span data-ttu-id="a42d6-121">[Definir e recuperar informações de versão](../../2014/database-engine/set-and-retrieve-version-information.md) </span><span class="sxs-lookup"><span data-stu-id="a42d6-121">[Set and Retrieve Version Information](../../2014/database-engine/set-and-retrieve-version-information.md) </span></span>  
 <span data-ttu-id="a42d6-122">[Exibir histórico do projeto](../../2014/database-engine/view-project-history.md) </span><span class="sxs-lookup"><span data-stu-id="a42d6-122">[View Project History](../../2014/database-engine/view-project-history.md) </span></span>  
 [<span data-ttu-id="a42d6-123">Exibir status de arquivos</span><span class="sxs-lookup"><span data-stu-id="a42d6-123">View File Status</span></span>](../../2014/database-engine/view-file-status.md)  
  
  
