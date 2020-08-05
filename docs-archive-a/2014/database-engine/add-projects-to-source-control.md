---
title: Adicionar projetos ao controle do código-fonte | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- adding projects
- projects [SQL Server Management Studio], adding
ms.assetid: fd4616b2-a564-4a66-ac53-d1f5cba213c2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0afef4ef91e4d80db7e956d03a95a2ecffe1dc4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570847"
---
# <a name="add-projects-to-source-control"></a><span data-ttu-id="7b552-102">Adicionar projetos ao controle do código-fonte</span><span class="sxs-lookup"><span data-stu-id="7b552-102">Add Projects to Source Control</span></span>
  <span data-ttu-id="7b552-103">As soluções do [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] podem hospedar vários projetos de script.</span><span class="sxs-lookup"><span data-stu-id="7b552-103">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] solutions can host multiple script projects.</span></span> <span data-ttu-id="7b552-104">Como você adiciona um projeto ao controle do código-fonte depende do fato de a solução a que o projeto pertence estar sob controle do código-fonte.</span><span class="sxs-lookup"><span data-stu-id="7b552-104">How you add a project to source control depends upon whether the solution to which the project belongs is under source control.</span></span> <span data-ttu-id="7b552-105">Se a solução estiver sob controle do código-fonte, fazer check-in da solução adicionará automaticamente o projeto ao controle do código-fonte.</span><span class="sxs-lookup"><span data-stu-id="7b552-105">If the solution is under source control, checking in the solution automatically adds the project to source control.</span></span> <span data-ttu-id="7b552-106">Para obter mais informações sobre como fazer check-in de soluções, consulte [check in Files](../../2014/database-engine/check-in-files.md).</span><span class="sxs-lookup"><span data-stu-id="7b552-106">For more information about checking in solutions, see [Check In Files](../../2014/database-engine/check-in-files.md).</span></span>  
  
 <span data-ttu-id="7b552-107">Se a solução a que esse projeto pertence não estiver sob controle do código-fonte, você poderá adicionar essa solução ao controle, o que adicionará automaticamente os projetos da solução.</span><span class="sxs-lookup"><span data-stu-id="7b552-107">If the solution that this project belongs to is not under source control, you can add that solution to source control, which then automatically adds the solution's projects.</span></span> <span data-ttu-id="7b552-108">Para obter mais informações sobre como adicionar soluções ao controle do código-fonte, consulte [Adicionar soluções ao controle do código-fonte](../../2014/database-engine/add-solutions-to-source-control.md).</span><span class="sxs-lookup"><span data-stu-id="7b552-108">For more information about adding solutions to source control, see [Add Solutions to Source Control](../../2014/database-engine/add-solutions-to-source-control.md).</span></span>  
  
 <span data-ttu-id="7b552-109">Se você não quiser adicionar a solução ao controle do código-fonte, poderá usar o comando **Adicionar seleção ao controle do código-fonte** para adicionar o projeto manualmente.</span><span class="sxs-lookup"><span data-stu-id="7b552-109">If you do not want to add the solution to source control, you can use the **Add Selection to Source Control** command to add the project manually.</span></span>  
  
 <span data-ttu-id="7b552-110">Os objetos de banco de dados não são protegidos diretamente pelo provedor de controle do código-fonte, mas você pode criar scripts de objetos de banco de dados e salvá-los sob o controle do código-fonte.</span><span class="sxs-lookup"><span data-stu-id="7b552-110">Database objects are not directly protected by the source control provider, but you can create scripts of database objects and save the scripts under source control.</span></span>  
  
### <a name="to-add-a-project-to-source-control"></a><span data-ttu-id="7b552-111">Para adicionar um projeto ao controle do código-fonte</span><span class="sxs-lookup"><span data-stu-id="7b552-111">To add a project to source control</span></span>  
  
1.  <span data-ttu-id="7b552-112">No Gerenciador de Soluções, selecione um projeto.</span><span class="sxs-lookup"><span data-stu-id="7b552-112">In Solution Explorer, select a project.</span></span>  
  
2.  <span data-ttu-id="7b552-113">No menu **arquivo** , aponte para **controle do código-fonte**e, em seguida, clique em **adicionar projetos selecionados ao controle do código-fonte**.</span><span class="sxs-lookup"><span data-stu-id="7b552-113">On the **File** menu, point to **Source Control**, and then click **Add Selected Projects to Source Control**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7b552-114">Se você usar o comando **adicionar projetos selecionados ao controle do código-fonte** para adicionar um projeto que pertence a uma solução controlada por origem, será perguntado se deseja adicionar o projeto como uma subpasta da solução controlada por origem ou adicionar o projeto como uma pasta separada.</span><span class="sxs-lookup"><span data-stu-id="7b552-114">If you use the **Add Selected Projects to Source Control** command to add a project that belongs to a source-controlled solution, you are prompted whether you want to add the project as a subfolder of the source-controlled solution or to add the project as a separate folder.</span></span>  
  
3.  <span data-ttu-id="7b552-115">Se solicitado, faça logon em seu provedor de controle do código-fonte.</span><span class="sxs-lookup"><span data-stu-id="7b552-115">If prompted, log on to your source control provider.</span></span>  
  
4.  <span data-ttu-id="7b552-116">A caixa de diálogo **Adicionar ao projeto SourceSafe** é exibida.</span><span class="sxs-lookup"><span data-stu-id="7b552-116">The **Add to SourceSafe Project** dialog box appears.</span></span> <span data-ttu-id="7b552-117">O nome do seu projeto é exibido na caixa **projeto** .</span><span class="sxs-lookup"><span data-stu-id="7b552-117">The name of your project appears in the **Project** box.</span></span>  
  
5.  <span data-ttu-id="7b552-118">Na lista **pastas** , abra a pasta onde você deseja posicionar o projeto.</span><span class="sxs-lookup"><span data-stu-id="7b552-118">In the **Folders** list, open the folder where you want to place your project.</span></span> <span data-ttu-id="7b552-119">Como alternativa, você pode clicar em **criar** para criar uma pasta com o nome exibido na caixa **projeto** .</span><span class="sxs-lookup"><span data-stu-id="7b552-119">Alternatively, you can click **Create** to create a folder with the name displayed in the **Project** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b552-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7b552-120">See Also</span></span>  
 [<span data-ttu-id="7b552-121">Adicionar soluções e projetos ao controle do código-fonte</span><span class="sxs-lookup"><span data-stu-id="7b552-121">Add Solutions and Projects to Source Control</span></span>](../../2014/database-engine/add-solutions-and-projects-to-source-control.md)  
  
  
