---
title: Conectar-se a uma página réplicas secundárias existentes (Assistente para adicionar réplica e adicionar bancos de dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.addreplicawizard.connecttoreplicas.f1
- sql12.swb.adddatabasewizard.connecttoreplicas.f1
ms.assetid: 850f1bc8-d7d0-425c-bd7b-03f0e9d3348e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 80af8dfebd6e23a923ddf67438edabf9ab0e2f65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679530"
---
# <a name="connect-to-existing-secondary-replicas-page-add-replica-wizard-and-add-databases-wizard"></a><span data-ttu-id="3a929-102">Conectar-se à página Réplicas Secundárias Existentes (Assistente de Adição de Réplica e Assistente de Adição de Bancos de Dados)</span><span class="sxs-lookup"><span data-stu-id="3a929-102">Connect to Existing Secondary Replicas Page (Add Replica Wizard and Add Databases Wizard)</span></span>
  <span data-ttu-id="3a929-103"> Este tópico descreve as opções da página **Conectar a Réplicas Secundárias Existentes**.</span><span class="sxs-lookup"><span data-stu-id="3a929-103">This help topic describes the options of the **Connect to Existing Secondary Replicas** page.</span></span> <span data-ttu-id="3a929-104">Este tópico é usado por [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)] e [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] do [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a929-104">This topic is used by the [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)] and [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="3a929-105">**Colunas da grade:**</span><span class="sxs-lookup"><span data-stu-id="3a929-105">**Grid columns:**</span></span>  
 <span data-ttu-id="3a929-106">**Instância do Servidor**</span><span class="sxs-lookup"><span data-stu-id="3a929-106">**Server Instance**</span></span>  
 <span data-ttu-id="3a929-107">Exibe o nome da instância de servidor que hospedará a réplica de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="3a929-107">Displays the name of the server instance that will host the availability replica.</span></span>  
  
 <span data-ttu-id="3a929-108">**Conectado como**</span><span class="sxs-lookup"><span data-stu-id="3a929-108">**Connected As**</span></span>  
 <span data-ttu-id="3a929-109">Exibe a conta conectada à instância de servidor, após o estabelecimento da conexão.</span><span class="sxs-lookup"><span data-stu-id="3a929-109">Displays the account that is connected to the server instance, once the connection has been established.</span></span> <span data-ttu-id="3a929-110">Se essa coluna exibir "**Não Conectada**" para uma determinada instância de servidor, será necessário clicar no botão **Conectar** ou **Conectar Tudo** .</span><span class="sxs-lookup"><span data-stu-id="3a929-110">If this column displays "**Not Connected**" for a given server instance, you will need to click either the **Connect** or **Connect All** button.</span></span>  
  
 <span data-ttu-id="3a929-111">**Connect**</span><span class="sxs-lookup"><span data-stu-id="3a929-111">**Connect**</span></span>  
 <span data-ttu-id="3a929-112">Clique se essa instância de servidor estiver sendo executada sob uma conta diferente da de outras instâncias de servidor às quais você precisa se conectar.</span><span class="sxs-lookup"><span data-stu-id="3a929-112">Click if this server instance is running under a different account than other server instances to which you need to connect.</span></span>  
  
 <span data-ttu-id="3a929-113">**Conectar Tudo**</span><span class="sxs-lookup"><span data-stu-id="3a929-113">**Connect All**</span></span>  
 <span data-ttu-id="3a929-114">Somente clique se cada instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] à qual você precisar se conectar estiver sendo executada como um serviço na mesma conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="3a929-114">Click only if every instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to which you need to connect is running as a service in the same user account.</span></span>  
  
 <span data-ttu-id="3a929-115">**Cancelar**</span><span class="sxs-lookup"><span data-stu-id="3a929-115">**Cancel**</span></span>  
 <span data-ttu-id="3a929-116">Clique para cancelar o assistente.</span><span class="sxs-lookup"><span data-stu-id="3a929-116">Click to cancel the wizard.</span></span> <span data-ttu-id="3a929-117">Na página **Conectar a Réplicas Secundárias Existentes** , o cancelamento do assistente faz com que ele seja fechado sem executar ações.</span><span class="sxs-lookup"><span data-stu-id="3a929-117">On the **Connect to Existing Secondary Replica** page, cancelling the wizard cause it to exit without performing any actions.</span></span>  
  

  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="3a929-118">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="3a929-118">Related Tasks</span></span>  
  
-   [<span data-ttu-id="3a929-119">Usar o Assistente para Adicionar Réplica ao Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="3a929-119">Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="3a929-120">Usar o Assistente para Adicionar Banco de Dados ao Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="3a929-120">Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](availability-group-add-database-to-group-wizard.md)  
  

  
## <a name="see-also"></a><span data-ttu-id="3a929-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3a929-121">See Also</span></span>  
 [<span data-ttu-id="3a929-122">Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3a929-122">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
