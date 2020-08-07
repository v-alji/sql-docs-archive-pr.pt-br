---
title: Remover uma instância do SQL Server por meio do Utilitário do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.utility.remove.f1
ms.assetid: ae1d126a-46d2-47bf-b339-17c743df6491
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6c09897fcd3ac6d82308288391cf54176eef49d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583582"
---
# <a name="remove-an-instance-of-sql-server-from-the-sql-server-utility"></a><span data-ttu-id="5da13-102">Remover uma instância do SQL Server do Utilitário do SQL Server</span><span class="sxs-lookup"><span data-stu-id="5da13-102">Remove an Instance of SQL Server from the SQL Server Utility</span></span>
  <span data-ttu-id="5da13-103">Use as etapas a seguir para remover uma instância gerenciada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] por meio do Utilitário do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5da13-103">Use the following steps to remove a managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span> <span data-ttu-id="5da13-104">Este procedimento remove a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da exibição de lista do UCP e a coleta de dados do Utilitário do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é interrompida.</span><span class="sxs-lookup"><span data-stu-id="5da13-104">This procedure removes the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the UCP list view and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility data collection stops.</span></span> <span data-ttu-id="5da13-105">A instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não é desinstalada.</span><span class="sxs-lookup"><span data-stu-id="5da13-105">The instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not uninstalled.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5da13-106">Antes de realizar este procedimento para remover uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility, tenha certeza de que os serviços do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e SQL Server Agent estão sendo executados na instância a ser removida.</span><span class="sxs-lookup"><span data-stu-id="5da13-106">Before you use this procedure to remove an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility, make sure that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and SQL Server Agent services are running on the instance to remove.</span></span>  
  
1.  <span data-ttu-id="5da13-107">No Gerenciador do Utilitário no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], clique em **Instâncias Gerenciadas**.</span><span class="sxs-lookup"><span data-stu-id="5da13-107">From the Utility Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], click on **Managed Instances**.</span></span> <span data-ttu-id="5da13-108">Observe a exibição de lista das instâncias registradas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no painel de conteúdo do Gerenciador do Utilitário.</span><span class="sxs-lookup"><span data-stu-id="5da13-108">Observe the list view of managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in the Utility Explorer content pane.</span></span>  
  
2.  <span data-ttu-id="5da13-109">Na coluna **Nome de Instância do SQL Server** da exibição de lista, selecione a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a ser removida do Utilitário do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5da13-109">In the **SQL Server Instance Name** column of the list view, select the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance to remove from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span> <span data-ttu-id="5da13-110">Clique com o botão direito do mouse na instância a ser removida e selecione **Remover Instância Gerenciada...** .</span><span class="sxs-lookup"><span data-stu-id="5da13-110">Right-click on the instance to remove, and select **Remove Managed Instance...**.</span></span>  
  
3.  <span data-ttu-id="5da13-111">Especifique as credenciais com privilégios de administrador para a instância de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: Clique em **Conectar...** , verifique as informações na caixa de diálogo **Conectar ao Servidor** e clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="5da13-111">Specify credentials with administrator privileges for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: Click **Connect...**, verify the information in the **Connect to Server** dialog box, then click **Connect**.</span></span> <span data-ttu-id="5da13-112">Você verá as informações de logon na caixa de diálogo **Remover Instância Gerenciada** .</span><span class="sxs-lookup"><span data-stu-id="5da13-112">You will see the login information on the **Remove Managed Instance** dialog.</span></span>  
  
4.  <span data-ttu-id="5da13-113">Para confirmar a operação, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5da13-113">To confirm the operation, click **OK**.</span></span> <span data-ttu-id="5da13-114">Para encerrar a operação, clique em **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="5da13-114">To quit the operation, click **Cancel**.</span></span>  
  
## <a name="manually-remove-a-managed-instance-of-sql-server-from-a-sql-server-utility"></a><span data-ttu-id="5da13-115">Remover manualmente uma instância gerenciada do SQL Server do Utilitário do SQL Server</span><span class="sxs-lookup"><span data-stu-id="5da13-115">Manually Remove a Managed Instance of SQL Server from a SQL Server Utility</span></span>  
 <span data-ttu-id="5da13-116">Este procedimento remove a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da exibição de lista do UCP e interrompe a coleta de dados do Utilitário do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5da13-116">This procedure removes the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the UCP list view and stops [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility data collection.</span></span> <span data-ttu-id="5da13-117">A instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não é desinstalada.</span><span class="sxs-lookup"><span data-stu-id="5da13-117">The instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not uninstalled.</span></span>  
  
 <span data-ttu-id="5da13-118">Para usar o PowerShell para remover uma instância gerenciada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] por meio do Utilitário do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5da13-118">To use PowerShell to remove a managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span> <span data-ttu-id="5da13-119">Esse script executa as seguintes operações:</span><span class="sxs-lookup"><span data-stu-id="5da13-119">This script performs the following operations:</span></span>  
  
-   <span data-ttu-id="5da13-120">Obtém o UCP pelo nome da instância do servidor.</span><span class="sxs-lookup"><span data-stu-id="5da13-120">Gets the UCP by server instance name.</span></span>  
  
-   <span data-ttu-id="5da13-121">Remove a instância gerenciada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] por meio do Utilitário do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5da13-121">Removes the managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span>  
  
```powershell
# Get Ucp connection  
$UcpServerInstanceName = "ComputerName\InstanceName";  
$UtilityInstance = new-object -Type Microsoft.SqlServer.Management.Smo.Server $UcpServerInstanceName;  
$UcpConnection = new-object -Type Microsoft.SqlServer.Management.Sdk.Sfc.SqlStoreConnection $UtilityInstance.ConnectionContext.SqlConnectionObject;  
$Utility = [Microsoft.SqlServer.Management.Utility.Utility]::Connect($UcpConnection);  
  
# Now remove the ManagedInstance from the SQL Server Utility  
$ServerInstanceName = "ComputerName\InstanceName";  
$Instance = new-object -Type Microsoft.SqlServer.Management.Smo.Server $ServerInstanceName;  
$InstanceConnection = new-object -Type Microsoft.SqlServer.Management.Sdk.Sfc.SqlStoreConnection $Instance.ConnectionContext.SqlConnectionObject;  
$ManagedInstance = $Utility.ManagedInstances[$ServerInstanceName];  
$ManagedInstance.Remove($InstanceConnection);  
```  
  
<span data-ttu-id="5da13-122">É importante fazer referência ao nome da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instância exatamente como armazenado no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5da13-122">It's important to refer to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance name exactly as it is stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5da13-123">Em uma instância com diferenciação de maiúsculas e minúsculas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], você deve especificar o nome da instância usando exatamente as maiúsculas e minúsculas, conforme retornado por @@SERVERNAME.</span><span class="sxs-lookup"><span data-stu-id="5da13-123">On a case-sensitive instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you must specify the instance name using the exact casing as returned by @@SERVERNAME.</span></span> 

<span data-ttu-id="5da13-124">Para obter o nome de instância para a instância gerenciada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], execute esta consulta na instância gerenciada:</span><span class="sxs-lookup"><span data-stu-id="5da13-124">To get the instance name for the managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], run this query on the managed instance:</span></span>  
  
```sql
select @@SERVERNAME AS instance_name  
```  
  
 <span data-ttu-id="5da13-125">Neste momento, a instância gerenciada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é removida completamente do UCP.</span><span class="sxs-lookup"><span data-stu-id="5da13-125">At this point, the managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is fully removed from the UCP.</span></span> <span data-ttu-id="5da13-126">Ela desaparece da exibição de lista da próxima vez que você atualizar os dados para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span><span class="sxs-lookup"><span data-stu-id="5da13-126">It disappears from the list view the next time you refresh data for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span> <span data-ttu-id="5da13-127">Este estado é idêntico para um usuário que consegue remover uma instância gerenciada na interface de usuário do SSMS.</span><span class="sxs-lookup"><span data-stu-id="5da13-127">This state is identical to a user successfully going through the remove managed instance operation in the SSMS user interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5da13-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5da13-128">See Also</span></span>  
 <span data-ttu-id="5da13-129">[Usar o Gerenciador do Utilitário para gerenciar o Utilitário do SQL Server](use-utility-explorer-to-manage-the-sql-server-utility.md) </span><span class="sxs-lookup"><span data-stu-id="5da13-129">[Use Utility Explorer to Manage the SQL Server Utility](use-utility-explorer-to-manage-the-sql-server-utility.md) </span></span>  
 [<span data-ttu-id="5da13-130">Solucionar problemas do Utilitário do SQL Server</span><span class="sxs-lookup"><span data-stu-id="5da13-130">Troubleshoot the SQL Server Utility</span></span>](../../database-engine/troubleshoot-the-sql-server-utility.md)  
