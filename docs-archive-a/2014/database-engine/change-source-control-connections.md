---
title: Alterar conexões de controle do código-fonte | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- connections [SQL Server Management Studio], source controls
- source controls [SQL Server Management Studio], connections
ms.assetid: 538e3beb-f99c-4095-bd65-6413e872d26e
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 077a09cdca0c0aff777184f04467ca39592690aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575372"
---
# <a name="change-source-control-connections"></a><span data-ttu-id="11a44-102">Alterar conexões de controle do código-fonte</span><span class="sxs-lookup"><span data-stu-id="11a44-102">Change Source Control Connections</span></span>
  <span data-ttu-id="11a44-103">A primeira vez que você adiciona ou abre uma solução de controle do código-fonte, seu provedor cria uma associação entre a pasta raiz do diretório da solução local e a pasta do servidor correspondente.</span><span class="sxs-lookup"><span data-stu-id="11a44-103">The first time you add or open a solution from source control, your source control provider creates an association between the root folder of the local solution directory and its corresponding server folder.</span></span>  
  
 <span data-ttu-id="11a44-104">A pasta raiz (também chamada de raiz unificada) reside no cliente.</span><span class="sxs-lookup"><span data-stu-id="11a44-104">The root folder (also called unified root) resides on the client.</span></span> <span data-ttu-id="11a44-105">Ela é a pasta abaixo da qual podem ser encontrados todos os arquivos referenciados por uma solução ou um projeto.</span><span class="sxs-lookup"><span data-stu-id="11a44-105">It is the folder beneath which all the files referenced by a solution or project can be found.</span></span> <span data-ttu-id="11a44-106">Para encontrar a versão mais recente de uma solução, seu histórico e suas informações de status, localize a pasta do servidor que reside no servidor de controle do código-fonte.</span><span class="sxs-lookup"><span data-stu-id="11a44-106">To find the latest version of a solution, its history, and its status information, locate the server folder, which resides on the source control server.</span></span> <span data-ttu-id="11a44-107">No [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe, as pastas do servidor são chamadas de projetos.</span><span class="sxs-lookup"><span data-stu-id="11a44-107">In [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe, server folders are called projects.</span></span>  
  
 <span data-ttu-id="11a44-108">Em muitas situações, você precisa desassociar ou desconectar uma solução de sua pasta do servidor.</span><span class="sxs-lookup"><span data-stu-id="11a44-108">In many situations, you need to unbind or disconnect a solution from its server folder.</span></span> <span data-ttu-id="11a44-109">Por exemplo, se o computador em que o provedor de controle do código-fonte reside estiver indisponível, você poderá fazer a conexão com um computador de backup, associar novamente sua solução a uma pasta do servidor salva e retomar o trabalho normalmente.</span><span class="sxs-lookup"><span data-stu-id="11a44-109">For example, if the computer on which your source control provider resides is unavailable, you can connect to a backup computer, rebind your solution to a backed-up server folder, and resume working normally.</span></span> <span data-ttu-id="11a44-110">Além disso, se um projeto de controle do código-fonte estiver bifurcado, você poderá ter que associar sua solução à pasta do servidor em que a nova versão de projeto reside.</span><span class="sxs-lookup"><span data-stu-id="11a44-110">Also, if a source control project is forked, you may have to bind your solution to the server folder where the new project version resides.</span></span>  
  
 <span data-ttu-id="11a44-111">Use a interface de usuário do provedor de controle do código-fonte para alterar a pasta do servidor a que a solução está associada.</span><span class="sxs-lookup"><span data-stu-id="11a44-111">Use the user interface of the source control provider to change the server folder that a solution is bound to.</span></span> <span data-ttu-id="11a44-112">É possível abrir a interface de usuário de controle do código-fonte no ambiente do [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="11a44-112">You can open the source control user interface from within the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] environment.</span></span>  
  
#### <a name="to-open-the-source-control-user-interface-from-the-studio-environment"></a><span data-ttu-id="11a44-113">Para abrir a interface de usuário de controle do código-fonte do ambiente do Studio</span><span class="sxs-lookup"><span data-stu-id="11a44-113">To open the source control user interface from the Studio environment</span></span>  
  
1.  <span data-ttu-id="11a44-114">No menu **arquivo** , aponte para **controle do código-fonte**e clique em **iniciar o Microsoft Visual SourceSafe**.</span><span class="sxs-lookup"><span data-stu-id="11a44-114">On the **File** menu, point to **Source Control**, and then click **Launch Microsoft Visual SourceSafe**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11a44-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="11a44-115">See Also</span></span>  
 <span data-ttu-id="11a44-116">[Noções básicas do controle do código-fonte](../../2014/database-engine/source-control-basics.md) </span><span class="sxs-lookup"><span data-stu-id="11a44-116">[Source Control Basics](../../2014/database-engine/source-control-basics.md) </span></span>  
 <span data-ttu-id="11a44-117">[Definir opções de controle do código-fonte](../../2014/database-engine/set-source-control-options.md) </span><span class="sxs-lookup"><span data-stu-id="11a44-117">[Set Source Control Options](../../2014/database-engine/set-source-control-options.md) </span></span>  
 [<span data-ttu-id="11a44-118">Excluir arquivos do controle do código-fonte</span><span class="sxs-lookup"><span data-stu-id="11a44-118">Exclude Files from Source Control</span></span>](../../2014/database-engine/exclude-files-from-source-control.md)  
  
  
