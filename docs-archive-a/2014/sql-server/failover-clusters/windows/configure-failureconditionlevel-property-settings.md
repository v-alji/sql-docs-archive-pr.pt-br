---
title: Definir as configurações da propriedade FailureConditionLevel | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
ms.assetid: 513dd179-9a46-46da-9fdd-7632cf6d0816
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8924b864d7cc8be078b370e3182713114f54ff6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573576"
---
# <a name="configure-failureconditionlevel-property-settings"></a><span data-ttu-id="810cb-102">Definir as configurações da propriedade FailureConditionLevel</span><span class="sxs-lookup"><span data-stu-id="810cb-102">Configure FailureConditionLevel Property Settings</span></span>
  <span data-ttu-id="810cb-103">Use a propriedade FailureConditionLevel para definir as condições da FCI AlwaysOn para failover ou reinicialização.</span><span class="sxs-lookup"><span data-stu-id="810cb-103">Use the FailureConditionLevel property to set the conditions for the AlwaysOn Failover Cluster Instance (FCI) to fail over or restart.</span></span> <span data-ttu-id="810cb-104">As alterações feitas nessa propriedade são aplicadas imediatamente, sem a necessidade de uma reinicialização do serviço WSFC (Windows Server Failover Cluster) ou do recurso FCI.</span><span class="sxs-lookup"><span data-stu-id="810cb-104">Changes to this property are applied immediately without requiring a restart of the Windows Server Failover Cluster (WSFC) service or the FCI resource.</span></span>  
  
-   <span data-ttu-id="810cb-105">**Antes de começar:**  [Configurações da propriedade FailureConditionLevel](#Restrictions), [Segurança](#Security)</span><span class="sxs-lookup"><span data-stu-id="810cb-105">**Before you begin:**  [FailureConditionLevel Property Settings](#Restrictions), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="810cb-106">**Para definir as configurações de propriedade de FailureConditionLevel usando:** [PowerShell](#PowerShellProcedure), [Gerenciador de Cluster de Failover](#WSFC) e [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="810cb-106">**To configure the FailureConditionLevel property settings using,** [PowerShell](#PowerShellProcedure), [Failover Cluster Manager](#WSFC), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="810cb-107">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="810cb-107">Before You Begin</span></span>  
  
###  <a name="failureconditionlevel-property-settings"></a><a name="Restrictions"></a> <span data-ttu-id="810cb-108">Configurações da propriedade FailureConditionLevel</span><span class="sxs-lookup"><span data-stu-id="810cb-108">FailureConditionLevel Property Settings</span></span>  
 <span data-ttu-id="810cb-109">As condições de falha são definidas em uma escala crescente.</span><span class="sxs-lookup"><span data-stu-id="810cb-109">The failure conditions are set on an increasing scale.</span></span> <span data-ttu-id="810cb-110">Para os níveis 1-5, cada um deles deve incluir todas as condições dos níveis anteriores, além de suas próprias condições.</span><span class="sxs-lookup"><span data-stu-id="810cb-110">For levels 1-5, each level includes all the conditions from the previous levels in addition to its own conditions.</span></span> <span data-ttu-id="810cb-111">Isso significa que, a cada nível, há uma probabilidade crescente de failover ou reinicialização.</span><span class="sxs-lookup"><span data-stu-id="810cb-111">This means that with each level, there is an increased probability of a failover or restart.</span></span>  <span data-ttu-id="810cb-112">Para obter mais informações, consulte a seção "Determinando falhas" do tópico [Failover Policy for Failover Cluster Instances](failover-policy-for-failover-cluster-instances.md) .</span><span class="sxs-lookup"><span data-stu-id="810cb-112">For more information, see the "Determining Failures" section of the [Failover Policy for Failover Cluster Instances](failover-policy-for-failover-cluster-instances.md) topic.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="810cb-113">Segurança</span><span class="sxs-lookup"><span data-stu-id="810cb-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="810cb-114">Permissões</span><span class="sxs-lookup"><span data-stu-id="810cb-114">Permissions</span></span>  
 <span data-ttu-id="810cb-115">Requer as permissões ALTER SETTINGS e VIEW SERVER STATE.</span><span class="sxs-lookup"><span data-stu-id="810cb-115">Requires ALTER SETTINGS and VIEW SERVER STATE permissions.</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="810cb-116">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="810cb-116">Using PowerShell</span></span>  
  
### <a name="to-configure-failureconditionlevel-settings"></a><span data-ttu-id="810cb-117">Para configurar a propriedade FailureConditionLevel</span><span class="sxs-lookup"><span data-stu-id="810cb-117">To configure FailureConditionLevel settings</span></span>  
  
1.  <span data-ttu-id="810cb-118">Inicie um Windows PowerShell elevado via **Executar como Administrador**.</span><span class="sxs-lookup"><span data-stu-id="810cb-118">Start an elevated Windows PowerShell via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="810cb-119">Importe o módulo `FailoverClusters` para habilitar cmdlets de cluster.</span><span class="sxs-lookup"><span data-stu-id="810cb-119">Import the `FailoverClusters` module to enable cluster cmdlets.</span></span>  
  
3.  <span data-ttu-id="810cb-120">Use o `Get-ClusterResource` cmdlet para localizar o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] recurso e, em seguida, use o `Set-ClusterParameter` cmdlet para definir a propriedade **FailureConditionLevel** para uma instância de cluster de failover.</span><span class="sxs-lookup"><span data-stu-id="810cb-120">Use the `Get-ClusterResource` cmdlet to find the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resource, then use `Set-ClusterParameter` cmdlet to set the **FailureConditionLevel** property for a Failover Cluster Instance.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="810cb-121">Sempre que você abrir uma nova janela do PowerShell, deverá importar o módulo `FailoverClusters`.</span><span class="sxs-lookup"><span data-stu-id="810cb-121">Every time you open a new PowerShell window, you need to import the `FailoverClusters` module.</span></span>  

 <span data-ttu-id="810cb-122">O exemplo a seguir altera a configuração FailureConditionLevel no recurso " [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] " do`SQL Server (INST1)`para fazer failover ou reiniciar em erros de servidor críticos.</span><span class="sxs-lookup"><span data-stu-id="810cb-122">The following example changes the FailureConditionLevel setting on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resource "`SQL Server (INST1)`" to fail over or restart on critical server errors.</span></span>  
  
```powershell  
Import-Module FailoverClusters  
  
$fci = "SQL Server (INST1)"  
Get-ClusterResource $fci | Set-ClusterParameter FailureConditionLevel 3
```  
  
### <a name="related-content-powershell"></a><span data-ttu-id="810cb-123">Conteúdo relacionado (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="810cb-123">Related Content (PowerShell)</span></span>  
  
-   <span data-ttu-id="810cb-124">[Clustering e alta disponibilidade](https://techcommunity.microsoft.com/t5/failover-clustering/bg-p/FailoverClustering) (Blog da equipe de Clustering de Failover e Balanceamento de Carga de Rede)</span><span class="sxs-lookup"><span data-stu-id="810cb-124">[Clustering and High-Availability](https://techcommunity.microsoft.com/t5/failover-clustering/bg-p/FailoverClustering) (Failover Clustering and Network Load Balancing Team Blog)</span></span>  
  
-   <span data-ttu-id="810cb-125">[Guia de Introdução ao Windows PowerShell em um cluster de failover](https://technet.microsoft.com/library/ee619762\(WS.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="810cb-125">[Getting Started with Windows PowerShell on a Failover Cluster](https://technet.microsoft.com/library/ee619762\(WS.10\).aspx)</span></span>  
  
-   [<span data-ttu-id="810cb-126">Comandos de recursos de cluster e cmdlets equivalentes no Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="810cb-126">Cluster resource commands and equivalent Windows PowerShell cmdlets</span></span>](https://msdn.microsoft.com/library/ee619744.aspx#BKMK_resource)  
  
##  <a name="using-the-failover-cluster-manager-snap-in"></a><a name="WSFC"></a> <span data-ttu-id="810cb-127">Usando o snap-in Gerenciador de Cluster de Failover</span><span class="sxs-lookup"><span data-stu-id="810cb-127">Using the Failover Cluster Manager Snap-in</span></span>  

### <a name="to-configure-failureconditionlevel-property-settings"></a><span data-ttu-id="810cb-128">Para definir as configurações da propriedade FailureConditionLevel</span><span class="sxs-lookup"><span data-stu-id="810cb-128">To configure FailureConditionLevel property settings</span></span>
  
1.  <span data-ttu-id="810cb-129">Abra o snap-in Gerenciador de Cluster de Failover.</span><span class="sxs-lookup"><span data-stu-id="810cb-129">Open the Failover Cluster Manager snap-in.</span></span>  
  
2.  <span data-ttu-id="810cb-130">Expanda **Serviços e Aplicativos** e selecione a FCI.</span><span class="sxs-lookup"><span data-stu-id="810cb-130">Expand the **Services and Applications** and select the FCI.</span></span>  
  
3.  <span data-ttu-id="810cb-131">Clique com o botão direito do mouse em **Recurso do SQL Server** em **Outros Recursos**e selecione **Propriedades** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="810cb-131">Right-click the **SQL Server resource** under **Other Resources**, and then select **Properties** from the menu.</span></span> <span data-ttu-id="810cb-132">A caixa de diálogo **Propriedades** do recurso do SQL Server é aberta.</span><span class="sxs-lookup"><span data-stu-id="810cb-132">The SQL Server resource **Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="810cb-133">Selecione a guia **Propriedades** , insira o valor desejado para a propriedade **FaliureConditionLevel** propriedade e clique em **OK** para aplicar a alteração.</span><span class="sxs-lookup"><span data-stu-id="810cb-133">Select the **Properties** tab, enter the desired value for the **FaliureConditionLevel** property, and then click **OK** to apply the change.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="810cb-134">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="810cb-134">Using Transact-SQL</span></span>  

### <a name="to-configure-failureconditionlevel-property-settings"></a><span data-ttu-id="810cb-135">Para definir as configurações da propriedade FailureConditionLevel</span><span class="sxs-lookup"><span data-stu-id="810cb-135">To configure FailureConditionLevel property settings</span></span>
  
 <span data-ttu-id="810cb-136">Usando a instrução [ALTER SERVER CONFIGURATION](/sql/t-sql/statements/alter-server-configuration-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] , você pode especificar o valor da propriedade FailureConditionLevel.</span><span class="sxs-lookup"><span data-stu-id="810cb-136">Using the [ALTER SERVER CONFIGURATION](/sql/t-sql/statements/alter-server-configuration-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement, you can specify the FailureConditionLevel property value.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="810cb-137">Exemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="810cb-137">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="810cb-138">O exemplo a seguir define a propriedade FailureConditionLevel como 0, indicando que nenhum failover ou reinicialização será disparado automaticamente em nenhuma condição de falha.</span><span class="sxs-lookup"><span data-stu-id="810cb-138">The following example sets the FailureConditionLevel property to 0, indicating that failover or restart will not be triggered automatically on any failure conditions.</span></span>  
  
```sql
ALTER SERVER CONFIGURATION SET FAILOVER CLUSTER PROPERTY FailureConditionLevel = 0;  
```  
  
## <a name="see-also"></a><span data-ttu-id="810cb-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="810cb-139">See Also</span></span>  
 <span data-ttu-id="810cb-140">[sp_server_diagnostics &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="810cb-140">[sp_server_diagnostics &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) </span></span>  
 [<span data-ttu-id="810cb-141">Failover Policy for Failover Cluster Instances</span><span class="sxs-lookup"><span data-stu-id="810cb-141">Failover Policy for Failover Cluster Instances</span></span>](failover-policy-for-failover-cluster-instances.md)  
