---
title: Como gerenciar um serviço CDC local | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 7f9be649-cd93-40c1-bc48-0480106f207c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 437590d4b91f2fc80d5bb8a90251bf0dc7c8e18a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678272"
---
# <a name="how-to-manage-a-local-cdc-service"></a><span data-ttu-id="0304f-102">Como gerenciar um serviço CDC local</span><span class="sxs-lookup"><span data-stu-id="0304f-102">How to Manage a Local CDC Service</span></span>
  <span data-ttu-id="0304f-103">Este procedimento descreve como usar o Console de Configuração do Serviço CDC para gerenciar os serviços CDC específicos.</span><span class="sxs-lookup"><span data-stu-id="0304f-103">This procedure describes how to use the CDC Service Configuration Console to manage specific CDC services.</span></span>  
  
### <a name="to-manage-a-specific-cdc-service"></a><span data-ttu-id="0304f-104">Para gerenciar um Serviço CDC específico</span><span class="sxs-lookup"><span data-stu-id="0304f-104">To manage a specific CDC Service</span></span>  
  
1.  <span data-ttu-id="0304f-105">No menu **Iniciar** , selecione **Configuração do Serviço CDC para Oracle**.</span><span class="sxs-lookup"><span data-stu-id="0304f-105">From the **Start** menu, select the **CDC Service Configuration for Oracle**.</span></span>  
  
2.  <span data-ttu-id="0304f-106">No painel esquerdo no Console de Configuração do Serviço CDC, expanda **Serviços Locais de CDC**.</span><span class="sxs-lookup"><span data-stu-id="0304f-106">From the left pane in the CDC Service Configuration Console, expand **Local CDC Services**.</span></span>  
  
3.  <span data-ttu-id="0304f-107">Selecione o serviço CDC com o qual você deseja trabalhar.</span><span class="sxs-lookup"><span data-stu-id="0304f-107">Select the CDC service you want to work with.</span></span>  
  
     <span data-ttu-id="0304f-108">Você também pode clicar com o botão direito no serviço CDC com o qual você deseja trabalhar e selecionar a ação desejada.</span><span class="sxs-lookup"><span data-stu-id="0304f-108">You can also right-click the CDC service you want to work with and select the desired action.</span></span>  
  
     <span data-ttu-id="0304f-109">**OR**</span><span class="sxs-lookup"><span data-stu-id="0304f-109">**OR**</span></span>  
  
     <span data-ttu-id="0304f-110">Selecione **Serviços Locais CDC** no painel esquerdo no Console de Configuração do Serviço CDC e selecione o serviço com o qual você quer trabalhar na seção do meio.</span><span class="sxs-lookup"><span data-stu-id="0304f-110">Select **Local CDC Services** from the left pane in the CDC Service Configuration Console then select the service you want to work with from the middle section of the CDC Service Configuration Console.</span></span>  
  
     <span data-ttu-id="0304f-111">Você também pode clicar com o botão direito no serviço CDC com o qual você deseja trabalhar e selecionar a ação desejada.</span><span class="sxs-lookup"><span data-stu-id="0304f-111">You can also right-click the CDC service you want to work with and select the desired action.</span></span>  
  
4.  <span data-ttu-id="0304f-112">Você pode realizar as seguintes tarefas ao trabalhar com um serviço CDC.</span><span class="sxs-lookup"><span data-stu-id="0304f-112">You can carry out the following tasks when working with a CDC service.</span></span>  
  
    -   <span data-ttu-id="0304f-113">**Excluir o serviço**</span><span class="sxs-lookup"><span data-stu-id="0304f-113">**Delete the service**</span></span>  
  
         <span data-ttu-id="0304f-114">No painel **Ações** no lado direito do Console de Configuração do Serviço CDC, clique em **Excluir** para excluir o serviço.</span><span class="sxs-lookup"><span data-stu-id="0304f-114">From the **Actions** pane on the right side of the CDC Service Configuration Console, click **Delete** to delete the service.</span></span>  
  
         <span data-ttu-id="0304f-115">Você também pode clicar com o botão direito do mouse no serviço CDC que deseja excluir e selecionar **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="0304f-115">You can also right-click the CDC service you want to delete and select **Delete**.</span></span>  
  
         <span data-ttu-id="0304f-116">**Observação**: se o serviço estiver sendo executado ao excluir o serviço, ele será parado antes de ser excluído.</span><span class="sxs-lookup"><span data-stu-id="0304f-116">**Note**: If the service is running when deleting the service, the service is stopped before being deleted.</span></span>  
  
         <span data-ttu-id="0304f-117">Para excluir uma definição de Serviço do Windows do Oracle CDC, o programa precisa de acesso de atualização ao banco de dados MSXDBCDC na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] associada.</span><span class="sxs-lookup"><span data-stu-id="0304f-117">To delete an Oracle CDC Windows Service definition, the program needs update access to the MSXDBCDC database in the associated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="0304f-118">Quando você clicar em **OK** para excluir o serviço, o programa tentará excluir o registro do Serviço Oracle CDC no banco de dados MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="0304f-118">When you click **OK** to delete the service, the program attempts to delete the Oracle CDC Service registration in the MSXDBCDC database.</span></span> <span data-ttu-id="0304f-119">Se falhar devido à falta de permissões, uma caixa de diálogo será exibida para pedir que o usuário insira um logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] com um acesso de atualização para o banco de dados MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="0304f-119">If it fails due to lack of permissions, a dialog box is displayed to prompt the user to enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login with an update access to the MSXDBCDC database.</span></span>  
  
         <span data-ttu-id="0304f-120">Para obter informações sobre os dados que você deverá inserir na caixa de diálogo Conecte-se ao SQL Server, consulte [Manage an Oracle CDC Service](manage-an-oracle-cdc-service.md) e [Connection to SQL Server for Delete](connection-to-sql-server-for-delete.md).</span><span class="sxs-lookup"><span data-stu-id="0304f-120">For information about the data you must enter in the Connect to SQL Server dialog box, see [Manage an Oracle CDC Service](manage-an-oracle-cdc-service.md) and [Connection to SQL Server for Delete](connection-to-sql-server-for-delete.md).</span></span>  
  
    -   <span data-ttu-id="0304f-121">**Editar as propriedades de serviço CDC**</span><span class="sxs-lookup"><span data-stu-id="0304f-121">**Edit the CDC Service Properties**</span></span>  
  
         <span data-ttu-id="0304f-122">No painel **Ações** no lado direito do Console de Configuração do Serviço CDC, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="0304f-122">From the **Actions** pane on the right side of the CDC Service Configuration Console, click **Properties**.</span></span>  
  
         <span data-ttu-id="0304f-123">Você também pode clicar com o botão direito do mouse no serviço CDC em que deseja editar as propriedades e selecionar **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="0304f-123">You can also right-click the CDC service where you want to edit the properties and select **Properties**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0304f-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0304f-124">See Also</span></span>  
 [<span data-ttu-id="0304f-125">Gerenciar um serviço Oracle CDC</span><span class="sxs-lookup"><span data-stu-id="0304f-125">Manage an Oracle CDC Service</span></span>](manage-an-oracle-cdc-service.md)  
  
  
