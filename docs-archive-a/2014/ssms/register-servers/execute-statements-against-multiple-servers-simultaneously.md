---
title: Executar instruções em vários servidores simultaneamente
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- multiserver queries
- executing queries against multiple servers
- queries [SQL Server], multiserver
ms.assetid: 197760f3-0a06-43de-8162-69c27d3fbe56
author: markingmyname
ms.author: maghan
ms.openlocfilehash: b94775029a1501d3e894d84ef4a027fc1595dc10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681334"
---
# <a name="execute-statements-against-multiple-servers-simultaneously-sql-server-management-studio"></a><span data-ttu-id="ef963-102">Execute Statements Against Multiple Servers Simultaneously (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="ef963-102">Execute Statements Against Multiple Servers Simultaneously (SQL Server Management Studio)</span></span>
  <span data-ttu-id="ef963-103">Este tópico descreve como consultar vários servidores ao mesmo tempo no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], criando um grupo de servidores locais ou um Servidor de Gerenciamento Central e um ou mais grupos de servidor, e um ou mais servidores registrados dentro dos grupos e, em seguida, consultar o grupo completo.</span><span class="sxs-lookup"><span data-stu-id="ef963-103">This topic describes how to query multiple servers at the same time in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], by creating a local server group, or a Central Management Server and one or more server groups, and one or more registered servers within the groups, and then querying the complete group.</span></span> <span data-ttu-id="ef963-104">Os resultados retornados pela consulta podem ser combinados em um único painel de resultados ou em painéis de resultados separados.</span><span class="sxs-lookup"><span data-stu-id="ef963-104">The results that are returned by the query can be combined into a single results pane, or can be returned in separate results panes.</span></span> <span data-ttu-id="ef963-105">O conjunto de resultados pode incluir colunas adicionais para o nome de servidor e o login que é usado pela consulta em cada servidor.</span><span class="sxs-lookup"><span data-stu-id="ef963-105">The results set can include additional columns for the server name and the login that is used by the query on each server.</span></span> <span data-ttu-id="ef963-106">Os servidores de gerenciamento centrais e os servidores registrados subordinados podem ser registrados somente com o uso da Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="ef963-106">Central Management Servers and subordinate servers can be registered by using only Windows Authentication.</span></span> <span data-ttu-id="ef963-107">Os servidores em grupos de servidores locais podem ser registrados usando Autenticação do Windows ou a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ef963-107">Servers in local server groups can be registered by using Windows Authentication or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ef963-108">Antes de executar os procedimentos a seguir, crie um Servidor de Gerenciamento Central e grupos de servidores.</span><span class="sxs-lookup"><span data-stu-id="ef963-108">Before you execute the following procedures, create a Central Management Server and server groups.</span></span> <span data-ttu-id="ef963-109">Para obter mais informações, consulte [Criar um servidor de gerenciamento central e um grupo de servidores &#40;SQL Server Management Studio&#41;](create-a-central-management-server-and-server-group.md).</span><span class="sxs-lookup"><span data-stu-id="ef963-109">For more information, see [Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;](create-a-central-management-server-and-server-group.md).</span></span>  
  
 <span data-ttu-id="ef963-110">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="ef963-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ef963-111">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="ef963-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ef963-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="ef963-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ef963-113">**Para executar instruções em vários servidores, usando:**</span><span class="sxs-lookup"><span data-stu-id="ef963-113">**To execute statements against multiple servers, using:**</span></span>  
  
     [<span data-ttu-id="ef963-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ef963-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ef963-115">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="ef963-115">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ef963-116">Segurança</span><span class="sxs-lookup"><span data-stu-id="ef963-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ef963-117">Permissões</span><span class="sxs-lookup"><span data-stu-id="ef963-117">Permissions</span></span>  
 <span data-ttu-id="ef963-118">Como as conexões mantidas por um Servidor de Gerenciamento Central são executadas no contexto do usuário com o uso da Autenticação do Windows, as permissões efetivas nos servidores registrados podem variar.</span><span class="sxs-lookup"><span data-stu-id="ef963-118">Because the connections maintained by a Central Management Server execute in the context of the user, by using Windows Authentication, the effective permissions on the registered servers might vary.</span></span> <span data-ttu-id="ef963-119">Por exemplo, o usuário pode ser membro da função de servidor fixa sysadmin na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] A, mas pode ter permissões limitadas na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] B.</span><span class="sxs-lookup"><span data-stu-id="ef963-119">For example, the user might be a member of the sysadmin fixed server role on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] A, but have limited permissions on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] B.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ef963-120">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ef963-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-execute-statements-against-multiple-configuration-targets-simultaneously"></a><span data-ttu-id="ef963-121">Para executar instruções em vários destinos de configuração simultaneamente</span><span class="sxs-lookup"><span data-stu-id="ef963-121">To execute statements against multiple configuration targets simultaneously</span></span>  
  
1.  <span data-ttu-id="ef963-122">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], no menu **Exibir** , clique em **Servidores Registrados**.</span><span class="sxs-lookup"><span data-stu-id="ef963-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Registered Servers**.</span></span>  
  
2.  <span data-ttu-id="ef963-123">Expanda um Servidor de Gerenciamento Central, clique com o botão direito do mouse em um grupo de servidores, aponte para **Conectar**e, em seguida, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="ef963-123">Expand a Central Management Server, right-click a server group, point to **Connect**, and then click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ef963-124">No Editor de Consultas, digite e execute uma instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] , como a seguinte:</span><span class="sxs-lookup"><span data-stu-id="ef963-124">In Query Editor, type and execute a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement, such as the following:</span></span>  
  
    ```  
    USE master  
    GO  
    SELECT * FROM sysdatabases;  
    GO  
    ```  
  
     <span data-ttu-id="ef963-125">Por padrão, o painel de resultados combinará os resultados da consulta de todos os servidores no grupo de servidor.</span><span class="sxs-lookup"><span data-stu-id="ef963-125">By default, the results pane will combine the query results from all the servers in the server group.</span></span>  
  
#### <a name="to-change-the-multiserver-results-options"></a><span data-ttu-id="ef963-126">Para alterar as opções de resultados de vários servidores</span><span class="sxs-lookup"><span data-stu-id="ef963-126">To change the multiserver results options</span></span>  
  
1.  <span data-ttu-id="ef963-127">No [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], no menu **Ferramentas** , clique em **Opções**.</span><span class="sxs-lookup"><span data-stu-id="ef963-127">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], on the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="ef963-128">Expanda **Resultados da Consulta**, expanda **SQL Server**e então clique em **Resultados de Multisservidor**.</span><span class="sxs-lookup"><span data-stu-id="ef963-128">Expand **Query Results**, expand **SQL Server**, and then click **Multiserver Results**.</span></span>  
  
3.  <span data-ttu-id="ef963-129">Na página **Resultados de Multisservidor** , especifique as configurações de opção que você quer e então clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ef963-129">On the **Multiserver Results** page, specify the option settings that you want, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef963-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ef963-130">See Also</span></span>  
 [<span data-ttu-id="ef963-131">Administrar vários servidores usando servidores de gerenciamento central</span><span class="sxs-lookup"><span data-stu-id="ef963-131">Administer Multiple Servers Using Central Management Servers</span></span>](../../relational-databases/administer-multiple-servers-using-central-management-servers.md)  
  
  
