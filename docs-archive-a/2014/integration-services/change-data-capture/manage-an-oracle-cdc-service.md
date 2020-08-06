---
title: Gerenciar um serviço Oracle CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- createSrv
ms.assetid: 5972cee3-b1a9-4c56-aed6-bdddf84af283
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f5fbe769980297a06b7958ecad04bfed85b9b714
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678912"
---
# <a name="manage-an-oracle-cdc-service"></a><span data-ttu-id="8aaca-102">Manage an Oracle CDC Service</span><span class="sxs-lookup"><span data-stu-id="8aaca-102">Manage an Oracle CDC Service</span></span>
  <span data-ttu-id="8aaca-103">Você pode usar o Console de Configuração do Serviço CDC para gerenciar um Serviço CDC específico.</span><span class="sxs-lookup"><span data-stu-id="8aaca-103">You can use the CDC Service Configuration Console to manage a specific CDC Service.</span></span>  
  
 <span data-ttu-id="8aaca-104">**Para selecionar o serviço CDC com o qual você deseja trabalhar**</span><span class="sxs-lookup"><span data-stu-id="8aaca-104">**To select the CDC service you want to work with**</span></span>  
  
1.  <span data-ttu-id="8aaca-105">No painel esquerdo no Console de Configuração do Serviço CDC, expanda **Serviços Locais de CDC**.</span><span class="sxs-lookup"><span data-stu-id="8aaca-105">From the left pane in the CDC Service Configuration Console, expand **Local CDC Services**.</span></span>  
  
2.  <span data-ttu-id="8aaca-106">Selecione o serviço CDC com o qual você deseja trabalhar.</span><span class="sxs-lookup"><span data-stu-id="8aaca-106">Select the CDC service you want to work with.</span></span>  
  
     <span data-ttu-id="8aaca-107">Você também pode clicar com o botão direito no serviço CDC com o qual você deseja trabalhar e selecionar a ação desejada.</span><span class="sxs-lookup"><span data-stu-id="8aaca-107">You can also right-click the CDC service you want to work with and select the desired action.</span></span> <span data-ttu-id="8aaca-108">Consulte [O que pode fazer você com um Serviço ](manage-an-oracle-cdc-service.md#BKMK_WhatcandowithCDCService).</span><span class="sxs-lookup"><span data-stu-id="8aaca-108">See [What can you do with a CDC Service](manage-an-oracle-cdc-service.md#BKMK_WhatcandowithCDCService).</span></span>  
  
 <span data-ttu-id="8aaca-109">**OR**</span><span class="sxs-lookup"><span data-stu-id="8aaca-109">**OR**</span></span>  
  
1.  <span data-ttu-id="8aaca-110">Selecione **Serviços Locais de CDC** no painel esquerdo no Console de Configuração do Serviço de CDC.</span><span class="sxs-lookup"><span data-stu-id="8aaca-110">Select **Local CDC Services** from the left pane in the CDC Service Configuration Console.</span></span>  
  
2.  <span data-ttu-id="8aaca-111">Da seção do meio do Console de Configuração do Serviço CDC, selecione o serviço com o qual você deseja trabalhar.</span><span class="sxs-lookup"><span data-stu-id="8aaca-111">From the middle section of the CDC Service Configuration Console, select the service you want to work with.</span></span>  
  
     <span data-ttu-id="8aaca-112">Você também pode clicar com o botão direito no serviço CDC com o qual você deseja trabalhar e selecionar a ação desejada.</span><span class="sxs-lookup"><span data-stu-id="8aaca-112">You can also right-click the CDC service you want to work with and select the desired action.</span></span> <span data-ttu-id="8aaca-113">Consulte [O que pode fazer você com um Serviço ](manage-an-oracle-cdc-service.md#BKMK_WhatcandowithCDCService).</span><span class="sxs-lookup"><span data-stu-id="8aaca-113">See [What can you do with a CDC Service](manage-an-oracle-cdc-service.md#BKMK_WhatcandowithCDCService).</span></span>  
  
##  <a name="what-can-you-do-with-a-cdc-service"></a><a name="BKMK_WhatcandowithCDCService"></a> <span data-ttu-id="8aaca-114">O que pode fazer você com um Serviço CDC</span><span class="sxs-lookup"><span data-stu-id="8aaca-114">What can you do with a CDC Service</span></span>  
 <span data-ttu-id="8aaca-115">Você pode realizar as seguintes ações ao trabalhar com um serviço CDC.</span><span class="sxs-lookup"><span data-stu-id="8aaca-115">You can carry out the following actions when working with a CDC service.</span></span>  
  
### <a name="delete-the-service"></a><span data-ttu-id="8aaca-116">Excluir o serviço</span><span class="sxs-lookup"><span data-stu-id="8aaca-116">Delete the service</span></span>  
 <span data-ttu-id="8aaca-117">No painel **Ações** no lado direito do Console de Configuração do Serviço CDC, clique em **Excluir** para excluir o serviço.</span><span class="sxs-lookup"><span data-stu-id="8aaca-117">From the **Actions** pane on the right side of the CDC Service Configuration Console, click **Delete** to delete the service.</span></span>  
  
 <span data-ttu-id="8aaca-118">Você também pode clicar com o botão direito do mouse no serviço CDC que deseja excluir e selecionar **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="8aaca-118">You can also right-click the CDC service you want to delete and select **Delete**.</span></span>  
  
 <span data-ttu-id="8aaca-119">**Observação**: se o serviço estiver sendo executado ao excluir o serviço, ele será parado antes de ser excluído.</span><span class="sxs-lookup"><span data-stu-id="8aaca-119">**Note**: If the service is running when deleting the service, the service is stopped before being deleted.</span></span>  
  
 <span data-ttu-id="8aaca-120">Para excluir a definição de Serviço do Windows do Oracle CDC, o programa precisa de acesso de atualização ao banco de dados MSXDBCDC na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] associada.</span><span class="sxs-lookup"><span data-stu-id="8aaca-120">To delete the Oracle CDC Windows Service definition, the program needs update access to the MSXDBCDC database in the associated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="8aaca-121">Quando você clicar em OK para excluir o serviço, o programa tentará excluir o registro do Serviço Oracle CDC no banco de dados MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="8aaca-121">When you click OK to delete the service, the program attempts to delete the Oracle CDC Service registration in the MSXDBCDC database.</span></span> <span data-ttu-id="8aaca-122">Se o programa não puder excluir o registro do Serviço Oracle CDC porque não tem as permissões corretas, ele solicitará que o usuário insira um logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] com permissões de atualização para o banco de dados MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="8aaca-122">If the program cannot delete the Oracle CDC Service registration because it does not have the proper permissions, it prompts the user to enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login with update permissions to the MSXDBCDC database.</span></span>  
  
 <span data-ttu-id="8aaca-123">Para obter informações sobre os dados que você deverá inserir na caixa de diálogo Conecte-se ao SQL Server, consulte [Connection to SQL Server for Delete](connection-to-sql-server-for-delete.md).</span><span class="sxs-lookup"><span data-stu-id="8aaca-123">For information about the data you must enter in the Connect to SQL Server dialog box, see [Connection to SQL Server for Delete](connection-to-sql-server-for-delete.md).</span></span>  
  
### <a name="edit-the-cdc-service-properties"></a><span data-ttu-id="8aaca-124">Editar as propriedades de serviço CDC</span><span class="sxs-lookup"><span data-stu-id="8aaca-124">Edit the CDC Service Properties</span></span>  
 <span data-ttu-id="8aaca-125">No painel **Ações** no lado direito do Console de Configuração do Serviço CDC, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="8aaca-125">From the **Actions** pane on the right side of the CDC Service Configuration Console, click **Properties**.</span></span>  
  
 <span data-ttu-id="8aaca-126">Você também pode clicar com o botão direito do mouse no serviço CDC em que deseja editar as propriedades e selecionar **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="8aaca-126">You can also right-click the CDC service where you want to edit the properties and select **Properties**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8aaca-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8aaca-127">See Also</span></span>  
 [<span data-ttu-id="8aaca-128">Como gerenciar um serviço CDC local</span><span class="sxs-lookup"><span data-stu-id="8aaca-128">How to Manage a Local CDC Service</span></span>](how-to-manage-a-local-cdc-service.md)  
