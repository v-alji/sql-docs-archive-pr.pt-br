---
title: Definir configurações da propriedade HealthCheckTimeout | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
ms.assetid: 3bbeb979-e6fc-4184-ad6e-cca62108de74
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a38cd6e9e4718a2f1c136e5412cde340e92f14c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573574"
---
# <a name="configure-healthchecktimeout-property-settings"></a><span data-ttu-id="a618c-102">Definir configurações da propriedade HealthCheckTimeout</span><span class="sxs-lookup"><span data-stu-id="a618c-102">Configure HealthCheckTimeout Property Settings</span></span>
  <span data-ttu-id="a618c-103">A configuração HealthCheckTimeout é usada para especificar o tempo, em milissegundos, que a DLL de recursos do SQL Server deve aguardar por informações retornadas pelo procedimento armazenado [sp_server_diagnostics](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) antes de relatar a FCI (Instância de Cluster de Failover) AlwaysOn como sem resposta.</span><span class="sxs-lookup"><span data-stu-id="a618c-103">The HealthCheckTimeout setting is used to specify the length of time, in milliseconds, that the SQL Server resource DLL should wait for information returned by the [sp_server_diagnostics](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) stored procedure before reporting the AlwaysOn Failover Cluster Instance (FCI) as unresponsive.</span></span> <span data-ttu-id="a618c-104">As alterações feitas nas configurações de tempo limite entram em vigor imediatamente e não requerem uma reinicialização do recurso do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a618c-104">Changes that are made to the timeout settings are effective immediately and do not require a restart of the SQL Server resource.</span></span>  
  
-   <span data-ttu-id="a618c-105">**Antes de começar:**  [Limitações e Restrições](#Limits), [Segurança](#Security)</span><span class="sxs-lookup"><span data-stu-id="a618c-105">**Before you begin:**  [Limitations and Restrictions](#Limits), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="a618c-106">**Para definir a configuração HeathCheckTimeout usando:**  [PowerShell](#PowerShellProcedure), [Gerenciador de Cluster de Failover](#WSFC), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="a618c-106">**To Configure the HeathCheckTimeout setting, using:**  [PowerShell](#PowerShellProcedure), [Failover Cluster Manager](#WSFC), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a618c-107">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="a618c-107">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Limits"></a> <span data-ttu-id="a618c-108">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="a618c-108">Limitations and Restrictions</span></span>  
 <span data-ttu-id="a618c-109">O valor padrão dessa propriedade é 60.000 milissegundos (60 segundos).</span><span class="sxs-lookup"><span data-stu-id="a618c-109">The default value for this property is 60,000 milliseconds (60 seconds).</span></span> <span data-ttu-id="a618c-110">O valor mínimo é 15.000 milissegundos (15 segundos).</span><span class="sxs-lookup"><span data-stu-id="a618c-110">The minimum value is 15,000 milliseconds (15 seconds).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a618c-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="a618c-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a618c-112">Permissões</span><span class="sxs-lookup"><span data-stu-id="a618c-112">Permissions</span></span>  
 <span data-ttu-id="a618c-113">Requer as permissões ALTER SETTINGS e VIEW SERVER STATE.</span><span class="sxs-lookup"><span data-stu-id="a618c-113">Requires ALTER SETTINGS and VIEW SERVER STATE permissions.</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="a618c-114">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="a618c-114">Using PowerShell</span></span>  
  
### <a name="to-configure-healthchecktimeout-settings"></a><span data-ttu-id="a618c-115">Para configurar HealthCheckTimeout</span><span class="sxs-lookup"><span data-stu-id="a618c-115">To configure HealthCheckTimeout settings</span></span>  
  
1.  <span data-ttu-id="a618c-116">Inicie um Windows PowerShell elevado via **Executar como Administrador**.</span><span class="sxs-lookup"><span data-stu-id="a618c-116">Start an elevated Windows PowerShell via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="a618c-117">Importe o módulo `FailoverClusters` para habilitar cmdlets de cluster.</span><span class="sxs-lookup"><span data-stu-id="a618c-117">Import the `FailoverClusters` module to enable cluster cmdlets.</span></span>  
  
3.  <span data-ttu-id="a618c-118">Use o `Get-ClusterResource` cmdlet para localizar o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] recurso e, em seguida, use o `Set-ClusterParameter` cmdlet para definir a propriedade **HealthCheckTimeout** para a instância de cluster de failover.</span><span class="sxs-lookup"><span data-stu-id="a618c-118">Use the `Get-ClusterResource` cmdlet to find the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resource, then use `Set-ClusterParameter` cmdlet to set the **HealthCheckTimeout** property for the failover cluster instance.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="a618c-119">Sempre que você abrir uma nova janela do PowerShell, deverá importar o módulo `FailoverClusters`.</span><span class="sxs-lookup"><span data-stu-id="a618c-119">Every time you open a new PowerShell window, you need to import the `FailoverClusters` module.</span></span>  

 <span data-ttu-id="a618c-120">O exemplo a seguir altera a configuração HealthCheckTimeout no recurso " [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] " do`SQL Server (INST1)`para 60.000 milissegundos.</span><span class="sxs-lookup"><span data-stu-id="a618c-120">The following example changes the HealthCheckTimeout setting on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resource "`SQL Server (INST1)`" to 60000 milliseconds.</span></span>  
  
```powershell  
Import-Module FailoverClusters  
  
$fci = "SQL Server (INST1)"  
Get-ClusterResource $fci | Set-ClusterParameter HealthCheckTimeout 60000  
```  
  
### <a name="related-content-powershell"></a><span data-ttu-id="a618c-121">Conteúdo relacionado (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="a618c-121">Related Content (PowerShell)</span></span>  
  
-   <span data-ttu-id="a618c-122">[Clustering e alta disponibilidade](https://techcommunity.microsoft.com/t5/failover-clustering/bg-p/FailoverClustering) (Blog da equipe de Clustering de Failover e Balanceamento de Carga de Rede)</span><span class="sxs-lookup"><span data-stu-id="a618c-122">[Clustering and High-Availability](https://techcommunity.microsoft.com/t5/failover-clustering/bg-p/FailoverClustering) (Failover Clustering and Network Load Balancing Team Blog)</span></span>  
  
-   <span data-ttu-id="a618c-123">[Guia de Introdução ao Windows PowerShell em um cluster de failover](https://technet.microsoft.com/library/ee619762\(WS.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="a618c-123">[Getting Started with Windows PowerShell on a Failover Cluster](https://technet.microsoft.com/library/ee619762\(WS.10\).aspx)</span></span>  
  
-   [<span data-ttu-id="a618c-124">Comandos de recursos de cluster e cmdlets equivalentes no Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a618c-124">Cluster resource commands and equivalent Windows PowerShell cmdlets</span></span>](https://msdn.microsoft.com/library/ee619744.aspx#BKMK_resource)  
  
##  <a name="using-the-failover-cluster-manager-snap-in"></a><a name="WSFC"></a> <span data-ttu-id="a618c-125">Usando o snap-in Gerenciador de Cluster de Failover</span><span class="sxs-lookup"><span data-stu-id="a618c-125">Using the Failover Cluster Manager Snap-in</span></span>  
 <span data-ttu-id="a618c-126">**Para definir a configuração HealthCheckTimeout**</span><span class="sxs-lookup"><span data-stu-id="a618c-126">**To configure HealthCheckTimeout setting**</span></span>  
  
1.  <span data-ttu-id="a618c-127">Abra o snap-in Gerenciador de Cluster de Failover.</span><span class="sxs-lookup"><span data-stu-id="a618c-127">Open the Failover Cluster Manager snap-in.</span></span>  
  
2.  <span data-ttu-id="a618c-128">Expanda **Serviços e Aplicativos** e selecione a FCI.</span><span class="sxs-lookup"><span data-stu-id="a618c-128">Expand **Services and Applications** and select the FCI.</span></span>  
  
3.  <span data-ttu-id="a618c-129">Clique com o botão direito do mouse em **Recurso de SQL Server** em **Outros Recursos** e selecione **Propriedades** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="a618c-129">Right-click the **SQL Server resource** under **Other Resources** and select **Properties** from the right-click menu.</span></span> <span data-ttu-id="a618c-130">A caixa de diálogo **Propriedades** do recurso do SQL Server é aberta.</span><span class="sxs-lookup"><span data-stu-id="a618c-130">The SQL Server resource **Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="a618c-131">Selecione a guia **Propriedades** , insira o valor desejado para a propriedade **HealthCheckTimeout** e clique em **OK** para aplicar a alteração.</span><span class="sxs-lookup"><span data-stu-id="a618c-131">Select the **Properties** tab, enter the desired value for the **HealthCheckTimeout** property, and then click **OK** to apply the change.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a618c-132">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a618c-132">Using Transact-SQL</span></span>  
 <span data-ttu-id="a618c-133">Usando a instrução [ALTER Server Configuration](/sql/t-sql/statements/alter-server-configuration-transact-sql) [!INCLUDE[tsql](../../../includes/tsql-md.md)] , você pode especificar o valor da propriedade HealthCheckTimeOut.</span><span class="sxs-lookup"><span data-stu-id="a618c-133">Using the [ALTER SERVER CONFIGURATION](/sql/t-sql/statements/alter-server-configuration-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement, you can specify the HealthCheckTimeOut property value.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="a618c-134">Exemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a618c-134">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="a618c-135">O exemplo a seguir define a opção HealthCheckTimeout como 15.000 milissegundos (15 segundos).</span><span class="sxs-lookup"><span data-stu-id="a618c-135">The following example sets the HealthCheckTimeout option to 15,000 milliseconds (15 seconds).</span></span>  
  
```sql
ALTER SERVER CONFIGURATION   
SET FAILOVER CLUSTER PROPERTY HealthCheckTimeout = 15000;  
```  
  
## <a name="see-also"></a><span data-ttu-id="a618c-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a618c-136">See Also</span></span>  
 [<span data-ttu-id="a618c-137">Failover Policy for Failover Cluster Instances</span><span class="sxs-lookup"><span data-stu-id="a618c-137">Failover Policy for Failover Cluster Instances</span></span>](failover-policy-for-failover-cluster-instances.md)  
