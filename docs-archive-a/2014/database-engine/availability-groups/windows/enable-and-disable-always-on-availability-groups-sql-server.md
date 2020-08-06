---
title: Habilitar e desabilitar Grupos de Disponibilidade AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], server instance
- Availability Groups [SQL Server], deploying
- Availability Groups [SQL Server], disabling
- Availability Groups [SQL Server], enabling
ms.assetid: 7c326958-5ae9-4761-9c57-905972276a8f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 585f1d86d328b7c5027241310108d102b56ca327
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570256"
---
# <a name="enable-and-disable-alwayson-availability-groups-sql-server"></a><span data-ttu-id="f24d8-102">Habilitar e desabilitar Grupos de Disponibilidade AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f24d8-102">Enable and Disable AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="f24d8-103">Habilitar o [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] é um pré-requisito para uma instância de servidor usar grupos de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="f24d8-103">Enabling [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] is a prerequisite for a server instance to use availability groups.</span></span> <span data-ttu-id="f24d8-104">Antes de poder criar e configurar qualquer grupo de disponibilidade, o recurso [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] deve ser habilitado em cada instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que hospedará uma réplica de disponibilidade de um ou mais grupos de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="f24d8-104">Before you can create and configure any availability group, the [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] feature must have been enabled on the each instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that will host an availability replica for one or more availability groups.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f24d8-105">Se você excluir e recriar um cluster WSFC, deverá desabilitar e reabilitar o recurso [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] em cada instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que hospedava uma réplica de disponibilidade no cluster WSFC original.</span><span class="sxs-lookup"><span data-stu-id="f24d8-105">If you delete and re-create a WSFC cluster, you must disable and re-enable the [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] feature on each instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosted an availability replica on the original WSFC cluster.</span></span>  
  
-   <span data-ttu-id="f24d8-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="f24d8-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f24d8-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="f24d8-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="f24d8-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="f24d8-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f24d8-109">**Como:**</span><span class="sxs-lookup"><span data-stu-id="f24d8-109">**How To:**</span></span>  
  
    -   [<span data-ttu-id="f24d8-110">Determinar se os Grupos de Disponibilidade AlwaysOn estão habilitados</span><span class="sxs-lookup"><span data-stu-id="f24d8-110">Determine Whether AlwaysOn Availability Groups is Enabled</span></span>](#IsEnabled)  
  
    -   [<span data-ttu-id="f24d8-111">Habilitar Grupos de Disponibilidade AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="f24d8-111">Enable AlwaysOn Availability Groups</span></span>](#EnableAOAG)  
  
    -   [<span data-ttu-id="f24d8-112">Desabilitar Grupos de Disponibilidade AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="f24d8-112">Disable AlwaysOn Availability Groups</span></span>](#DisableAOAG)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f24d8-113">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="f24d8-113">Before You Begin</span></span>  
  
###  <a name="prerequisites-for-enabling-alwayson-availability-groups"></a><a name="Prerequisites"></a><span data-ttu-id="f24d8-114">Pré-requisitos para habilitar o Grupos de Disponibilidade AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="f24d8-114">Prerequisites for Enabling AlwaysOn Availability Groups</span></span>  
  
-   <span data-ttu-id="f24d8-115">A instância de servidor deve residir em um nó WSFC (Windows Server Failover Clustering).</span><span class="sxs-lookup"><span data-stu-id="f24d8-115">The server instance must reside on a Windows Server Failover Clustering (WSFC) node.</span></span>  
  
-   <span data-ttu-id="f24d8-116">A instância de servidor deve estar executando uma edição do SQL Server com suporte para o [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f24d8-116">The server instance must be running an edition of SQL Server that supports [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span></span> <span data-ttu-id="f24d8-117">Para obter mais informações, consulte [recursos com suporte nas edições do SQL Server 2014](../../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="f24d8-117">For more information, see [Features Supported by the Editions of SQL Server 2014](../../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
-   <span data-ttu-id="f24d8-118">Habilitar Grupos de Disponibilidade AlwaysOn somente em uma instância de servidor de cada vez.</span><span class="sxs-lookup"><span data-stu-id="f24d8-118">Enable AlwaysOn Availability Groups on only one server instance at a time.</span></span> <span data-ttu-id="f24d8-119">Depois de habilitar os Grupos de Disponibilidade AlwaysOn, aguarde até que o serviço do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tenha reiniciado antes de seguir para a próxima instância de servidor.</span><span class="sxs-lookup"><span data-stu-id="f24d8-119">After enabling AlwaysOn Availability Groups, wait until the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service has restarted before you proceed to another server instance.</span></span>  
  
 <span data-ttu-id="f24d8-120">Para obter informações sobre os pré-requisitos adicionais para criar e configurar grupos de disponibilidade, consulte [pré-requisitos, restrições e recomendações para Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="f24d8-120">For information about additional prerequisites for creating and configuring availability groups, see [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f24d8-121">Segurança</span><span class="sxs-lookup"><span data-stu-id="f24d8-121">Security</span></span>  
 <span data-ttu-id="f24d8-122">Enquanto os Grupos de Disponibilidade AlwaysOn estiverem habilitados em uma instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], a instância de servidor terá total controle no cluster WSFC.</span><span class="sxs-lookup"><span data-stu-id="f24d8-122">While AlwaysOn Availability Groups is enabled on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the server instance has full control on the WSFC cluster.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f24d8-123">Permissões</span><span class="sxs-lookup"><span data-stu-id="f24d8-123">Permissions</span></span>  
 <span data-ttu-id="f24d8-124">Requer a associação ao grupo **Administrador** no computador local e o controle total no cluster WSFC.</span><span class="sxs-lookup"><span data-stu-id="f24d8-124">Requires membership in the **Administrator** group on the local computer and full control on the WSFC cluster.</span></span> <span data-ttu-id="f24d8-125">Quando for habilitar o AlwaysOn usando o PowerShell, abra a janela Prompt de Comando usando a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="f24d8-125">When enabling AlwaysOn by using PowerShell, open the Command Prompt window using the **Run as administrator** option.</span></span>  
  
 <span data-ttu-id="f24d8-126">Exige que o Active Directory crie objetos e gerencie permissões de objetos.</span><span class="sxs-lookup"><span data-stu-id="f24d8-126">Requires Active Directory Create Objects and Manage Objects permissions.</span></span>  
  
##  <a name="determine-whether-alwayson-availability-groups-is-enabled"></a><a name="IsEnabled"></a><span data-ttu-id="f24d8-127">Determinar se Grupos de Disponibilidade AlwaysOn está habilitado</span><span class="sxs-lookup"><span data-stu-id="f24d8-127">Determine Whether AlwaysOn Availability Groups is Enabled</span></span>  
  
-   [<span data-ttu-id="f24d8-128">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f24d8-128">SQL Server Management Studio</span></span>](#SSMS1Procedure)  
  
-   [<span data-ttu-id="f24d8-129">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f24d8-129">Transact-SQL</span></span>](#Tsql1Procedure)  
  
-   [<span data-ttu-id="f24d8-130">PowerShell</span><span class="sxs-lookup"><span data-stu-id="f24d8-130">PowerShell</span></span>](#PowerShell1Procedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMS1Procedure"></a> <span data-ttu-id="f24d8-131">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f24d8-131">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="f24d8-132">**Para determinar se os Grupos de Disponibilidade AlwaysOn estão habilitados**</span><span class="sxs-lookup"><span data-stu-id="f24d8-132">**To determine whether AlwaysOn Availability Groups is enabled**</span></span>  
  
1.  <span data-ttu-id="f24d8-133">No Pesquisador de Objetos, clique com o botão direito do mouse na instância de servidor e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="f24d8-133">In Object Explorer, right-click the server instance, and  click **Properties**.</span></span>  
  
2.  <span data-ttu-id="f24d8-134">Na caixa de diálogo **Propriedades do Servidor** , clique na página **Geral** .</span><span class="sxs-lookup"><span data-stu-id="f24d8-134">In the **Server Properties** dialog box, click the **General** page.</span></span> <span data-ttu-id="f24d8-135">A propriedade **Está habilitado para HADR** exibirá um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="f24d8-135">The **Is HADR Enabled** property displays one of the following values:</span></span>  
  
    -   <span data-ttu-id="f24d8-136">**True**, se os Grupos de Disponibilidade AlwaysOn estiverem habilitados</span><span class="sxs-lookup"><span data-stu-id="f24d8-136">**True**, if AlwaysOn Availability Groups is enabled</span></span>  
  
    -   <span data-ttu-id="f24d8-137">**False**, se os Grupos de Disponibilidade AlwaysOn estiverem desabilitados</span><span class="sxs-lookup"><span data-stu-id="f24d8-137">**False**, if AlwaysOn Availability Groups is disabled.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="Tsql1Procedure"></a> <span data-ttu-id="f24d8-138">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f24d8-138">Using Transact-SQL</span></span>  
 <span data-ttu-id="f24d8-139">**Para determinar se os Grupos de Disponibilidade AlwaysOn estão habilitados**</span><span class="sxs-lookup"><span data-stu-id="f24d8-139">**To determine whether AlwaysOn Availability Groups is enabled**</span></span>  
  
1.  <span data-ttu-id="f24d8-140">Use a seguinte instrução [SERVERPROPERTY](/sql/t-sql/functions/serverproperty-transact-sql) :</span><span class="sxs-lookup"><span data-stu-id="f24d8-140">Use the following [SERVERPROPERTY](/sql/t-sql/functions/serverproperty-transact-sql) statement:</span></span>  
  
    ```sql
    SELECT SERVERPROPERTY ('IsHadrEnabled');  
    ```  
  
     <span data-ttu-id="f24d8-141">A configuração da propriedade de servidor `IsHadrEnabled` indica se uma instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] está habilitada para Grupos de Disponibilidade AlwaysOn da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="f24d8-141">The setting of the `IsHadrEnabled` server property indicates whether an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is enabled for AlwaysOn Availability Groups, as follows:</span></span>  
  
    -   <span data-ttu-id="f24d8-142">Se `IsHadrEnabled` = 1, os Grupos de Disponibilidade AlwaysOn estão habilitados.</span><span class="sxs-lookup"><span data-stu-id="f24d8-142">If `IsHadrEnabled` = 1, AlwaysOn Availability Groups is enabled.</span></span>  
  
    -   <span data-ttu-id="f24d8-143">Se `IsHadrEnabled` = 0, os Grupos de Disponibilidade AlwaysOn estarão desabilitados.</span><span class="sxs-lookup"><span data-stu-id="f24d8-143">If `IsHadrEnabled` = 0, AlwaysOn Availability Groups is disabled.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f24d8-144">Para obter mais informações sobre a `IsHadrEnabled` propriedade de servidor, consulte [ServerProperty &#40;TRANSACT-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f24d8-144">For more information about the `IsHadrEnabled` server property, see [SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql).</span></span>  
  
###  <a name="using-powershell"></a><a name="PowerShell1Procedure"></a> <span data-ttu-id="f24d8-145">Uso do PowerShell</span><span class="sxs-lookup"><span data-stu-id="f24d8-145">Using PowerShell</span></span>  
 <span data-ttu-id="f24d8-146">**Para determinar se os Grupos de Disponibilidade AlwaysOn estão habilitados**</span><span class="sxs-lookup"><span data-stu-id="f24d8-146">**To determine whether AlwaysOn Availability Groups is enabled**</span></span>  
  
1.  <span data-ttu-id="f24d8-147">Defina default ( `cd` ) para a instância do servidor (por exemplo, `\SQL\NODE1\DEFAULT` ) na qual você deseja determinar se o [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] está habilitado.</span><span class="sxs-lookup"><span data-stu-id="f24d8-147">Set default (`cd`) to the server instance (e.g. `\SQL\NODE1\DEFAULT`) on which you want to determine whether [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] is enabled.</span></span>  
  
2.  <span data-ttu-id="f24d8-148">Digite o seguinte comando `Get-Item` do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f24d8-148">Enter the following PowerShell `Get-Item` command:</span></span>  
  
    ```powershell
    Get-Item . | Select IsHadrEnabled  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="f24d8-149">Para exibir a sintaxe de um cmdlet, use o cmdlet `Get-Help` no ambiente do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f24d8-149">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="f24d8-150">Para obter mais informações, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="f24d8-150">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="f24d8-151">**Para configurar e usar o provedor do SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f24d8-151">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="f24d8-152">Provedor do SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="f24d8-152">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="enable-alwayson-availability-groups"></a><a name="EnableAOAG"></a> <span data-ttu-id="f24d8-153">Habilitar Grupos de Disponibilidade AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="f24d8-153">Enable AlwaysOn Availability Groups</span></span>  
 <span data-ttu-id="f24d8-154">**Para habilitar o AlwaysOn, usando:**</span><span class="sxs-lookup"><span data-stu-id="f24d8-154">**To enable AlwaysOn, using:**</span></span>  
  
-   [<span data-ttu-id="f24d8-155">SQL Server Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f24d8-155">SQL Server Configuration Manager</span></span>](#SQLCM2Procedure)  
  
-   [<span data-ttu-id="f24d8-156">PowerShell</span><span class="sxs-lookup"><span data-stu-id="f24d8-156">PowerShell</span></span>](#PScmd2Procedure)  
  
###  <a name="using-sql-server-configuration-manager"></a><a name="SQLCM2Procedure"></a> <span data-ttu-id="f24d8-157">Usando o SQL Server Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f24d8-157">Using SQL Server Configuration Manager</span></span>  
 <span data-ttu-id="f24d8-158">**Para habilitar Grupos de Disponibilidade AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="f24d8-158">**To enable AlwaysOn Availability Groups**</span></span>  
  
1.  <span data-ttu-id="f24d8-159">Conecte-se ao nó do WSFC (Windows Server Failover Clustering) que hospeda a instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] onde você deseja habilitar Grupos de Disponibilidade AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="f24d8-159">Connect to the Windows Server Failover Clustering (WSFC) node that hosts the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance where you want to enable AlwaysOn Availability Groups.</span></span>  
  
2.  <span data-ttu-id="f24d8-160">No menu **Iniciar** , aponte para **Todos os Programas**, para [!INCLUDE[ssCurrentUI](../../../includes/sscurrentui-md.md)], para **Ferramentas de Configuração**e clique em **SQL Server Configuration Manager**.</span><span class="sxs-lookup"><span data-stu-id="f24d8-160">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and  click **SQL Server Configuration Manager**.</span></span>  
  
3.  <span data-ttu-id="f24d8-161">Em **SQL Server Configuration Manager**, clique em **serviços SQL Server**, clique com o botão direito do mouse em SQL Server (\*\* < *`instance name`*>)\*\*, em que **<*`instance name`*>** é o nome de uma instância de servidor local para a qual você deseja habilitar grupos de disponibilidade AlwaysOn e clique em **Propriedades.**</span><span class="sxs-lookup"><span data-stu-id="f24d8-161">In **SQL Server Configuration Manager**, click **SQL Server Services**, right-click SQL Server (**<*`instance name`*>)**, where **<*`instance name`*>** is the name of a local server instance for which you want to enable AlwaysOn Availability Groups, and click **Properties.**</span></span>  
  
4.  <span data-ttu-id="f24d8-162">Selecione a guia **Alta Disponibilidade AlwaysOn** .</span><span class="sxs-lookup"><span data-stu-id="f24d8-162">Select the **AlwaysOn High Availability** tab.</span></span>  
  
5.  <span data-ttu-id="f24d8-163">Verifique se o campo **Nome do cluster de failover do Windows** contém o nome do cluster de failover local.</span><span class="sxs-lookup"><span data-stu-id="f24d8-163">Verify that **Windows failover cluster name** field contains the name of the local failover cluster.</span></span> <span data-ttu-id="f24d8-164">Se esse campo estiver em branco, é porque essa instância de servidor não oferece suporte ao [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)]no momento.</span><span class="sxs-lookup"><span data-stu-id="f24d8-164">If this field is blank, this server instance currently does not support [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span></span> <span data-ttu-id="f24d8-165">Pode ser que o computador local não seja um nó de cluster, o cluster WSFC tenha sido desligado ou essa edição do [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] não ofereça suporte ao [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f24d8-165">Either the local computer is not a cluster node, the WSFC cluster has been shut down, or this edition of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] that does not support [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span></span>  
  
6.  <span data-ttu-id="f24d8-166">Marque a caixa de seleção **habilitar grupos de disponibilidade AlwaysOn** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f24d8-166">Select the **Enable AlwaysOn Availability Groups** check box, and click **OK**.</span></span>  
  
     [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="f24d8-167">Configuration Manager salva suas alterações.</span><span class="sxs-lookup"><span data-stu-id="f24d8-167">Configuration Manager saves your change.</span></span> <span data-ttu-id="f24d8-168">Em seguida, você deve reiniciar manualmente o serviço do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f24d8-168">Then, you must manually restart the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service.</span></span> <span data-ttu-id="f24d8-169">Isso permite escolher a hora de reinicialização mais adequada de acordo com as necessidades da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="f24d8-169">This enables you to choose a restart time that is best for your business requirements.</span></span> <span data-ttu-id="f24d8-170">Quando o serviço do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] for reiniciado, AlwaysOn será habilitado e a propriedade de servidor `IsHadrEnabled` será definida como 1.</span><span class="sxs-lookup"><span data-stu-id="f24d8-170">When the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service restarts, AlwaysOn will be enabled, and the `IsHadrEnabled` server property will be set to 1.</span></span>  
  
###  <a name="using-sql-server-powershell"></a><a name="PScmd2Procedure"></a> <span data-ttu-id="f24d8-171">Usando o SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="f24d8-171">Using SQL Server PowerShell</span></span>  
 <span data-ttu-id="f24d8-172">**Para habilitar o AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="f24d8-172">**To enable AlwaysOn**</span></span>  
  
1.  <span data-ttu-id="f24d8-173">Altere o diretório (`cd`) para uma instância de servidor que você queira habilitar para Grupos de Disponibilidade AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="f24d8-173">Change directory (`cd`) to a server instance that you want to enable for AlwaysOn Availability Groups.</span></span>  
  
2.  <span data-ttu-id="f24d8-174">Use o cmdlet `Enable-SqlAlwaysOn` para habilitar Grupos de Disponibilidade AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="f24d8-174">Use the `Enable-SqlAlwaysOn` cmdlet to enable AlwaysOn Availability Groups.</span></span>  
  
     <span data-ttu-id="f24d8-175">Para exibir a sintaxe de um cmdlet, use o cmdlet `Get-Help` no ambiente do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f24d8-175">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="f24d8-176">Para obter mais informações, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="f24d8-176">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f24d8-177">Para obter informações sobre como controlar se o `Enable-SqlAlwaysOn` cmdlet reinicia o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] serviço, consulte [quando um cmdlet reinicia o serviço de SQL Server?](#WhenCmdletRestartsSQL), mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="f24d8-177">For information about how to control whether the `Enable-SqlAlwaysOn` cmdlet restarts the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service, see [When Does a Cmdlet Restart the SQL Server Service?](#WhenCmdletRestartsSQL), later in this topic.</span></span>  
  
 <span data-ttu-id="f24d8-178">**Para configurar e usar o provedor do SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f24d8-178">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="f24d8-179">Provedor do SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="f24d8-179">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
####  <a name="example-enable-sqlalwayson"></a><a name="ExmplEnable-SqlHadrServic"></a> <span data-ttu-id="f24d8-180">Exemplo: Enable-SqlAlwaysOn</span><span class="sxs-lookup"><span data-stu-id="f24d8-180">Example: Enable-SqlAlwaysOn</span></span>  
 <span data-ttu-id="f24d8-181">O comando do PowerShell a seguir habilita o [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] em uma instância do SQL Server (*Computer*\\*Instance*).</span><span class="sxs-lookup"><span data-stu-id="f24d8-181">The following PowerShell command enables [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] on an instance of SQL Server (*Computer*\\*Instance*).</span></span>  
  
```powershell
Enable-SqlAlwaysOn -Path SQLSERVER:\SQL\Computer\Instance  
```  
  
##  <a name="disable-alwayson-availability-groups"></a><a name="DisableAOAG"></a><span data-ttu-id="f24d8-182">Desabilitar Grupos de Disponibilidade AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="f24d8-182">Disable AlwaysOn Availability Groups</span></span>  
  
-   <span data-ttu-id="f24d8-183">**Antes de você desabilitar o AlwaysOn:**</span><span class="sxs-lookup"><span data-stu-id="f24d8-183">**Before you disable AlwaysOn:**</span></span>  
  
     [<span data-ttu-id="f24d8-184">Recomendações</span><span class="sxs-lookup"><span data-stu-id="f24d8-184">Recommendations</span></span>](#Recommendations)  
  
-   <span data-ttu-id="f24d8-185">**Para desabilitar o AlwaysOn, usando:**</span><span class="sxs-lookup"><span data-stu-id="f24d8-185">**To disable AlwaysOn, using:**</span></span>  
  
    -   [<span data-ttu-id="f24d8-186">SQL Server Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f24d8-186">SQL Server Configuration Manager</span></span>](#SQLCM3Procedure)  
  
    -   [<span data-ttu-id="f24d8-187">PowerShell</span><span class="sxs-lookup"><span data-stu-id="f24d8-187">PowerShell</span></span>](#PScmd3Procedure)  
  
-   <span data-ttu-id="f24d8-188">**Acompanhamento:**  [depois de desabilitar o AlwaysOn](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="f24d8-188">**Follow Up:**  [After Disabling AlwaysOn](#FollowUp)</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f24d8-189">Desabilite AlwaysOn em somente uma instância de servidor de cada vez.</span><span class="sxs-lookup"><span data-stu-id="f24d8-189">Disable AlwaysOn on only one server instance at a time.</span></span> <span data-ttu-id="f24d8-190">Depois de desabilitar os Grupos de Disponibilidade AlwaysOn, aguarde até que o serviço do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tenha reiniciado antes de seguir para a próxima instância de servidor.</span><span class="sxs-lookup"><span data-stu-id="f24d8-190">After disabling AlwaysOn Availability Groups, wait until the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service has restarted before you proceed to another server instance.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="f24d8-191">Recomendações</span><span class="sxs-lookup"><span data-stu-id="f24d8-191">Recommendations</span></span>  
 <span data-ttu-id="f24d8-192">Antes de você desabilitar o AlwaysOn em uma instância de servidor, nós recomendamos que você faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f24d8-192">Before you disable AlwaysOn on a server instance, we recommend that you do the following:</span></span>  
  
1.  <span data-ttu-id="f24d8-193">Se a instância de servidor estiver hospedando a réplica primária de um grupo de disponibilidade que você deseja manter, nós recomendaremos que você realize manualmente o failover do grupo de disponibilidade para uma réplica secundária sincronizada, se possível.</span><span class="sxs-lookup"><span data-stu-id="f24d8-193">If the server instance is currently hosting the primary replica of an availability group that you want to keep, we recommend that you manually fail over the availability group to a synchronized secondary replica, if possible.</span></span> <span data-ttu-id="f24d8-194">Para obter mais informações, veja [Executar um failover manual planejado de um grupo de disponibilidade &#40;SQL Server&#41;](perform-a-planned-manual-failover-of-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f24d8-194">For more information, see [Perform a Planned Manual Failover of an Availability Group &#40;SQL Server&#41;](perform-a-planned-manual-failover-of-an-availability-group-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="f24d8-195">Remova todas as réplicas secundárias locais.</span><span class="sxs-lookup"><span data-stu-id="f24d8-195">Remove all local secondary replicas.</span></span> <span data-ttu-id="f24d8-196">Para obter mais informações, veja [Remover uma réplica secundária de um grupo de disponibilidade &#40;SQL Server&#41;](remove-a-secondary-replica-from-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f24d8-196">For more information, see [Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;](remove-a-secondary-replica-from-an-availability-group-sql-server.md).</span></span>  
  
###  <a name="using-sql-server-configuration-manager"></a><a name="SQLCM3Procedure"></a> <span data-ttu-id="f24d8-197">Usando o SQL Server Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f24d8-197">Using SQL Server Configuration Manager</span></span>  
 <span data-ttu-id="f24d8-198">**Para desabilitar o AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="f24d8-198">**To disable AlwaysOn**</span></span>  
  
1.  <span data-ttu-id="f24d8-199">Conecte-se ao nó do WSFC (Windows Server Failover Clustering) que hospeda a instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] onde você deseja desabilitar Grupos de Disponibilidade AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="f24d8-199">Connect to the Windows Server Failover Clustering (WSFC) node that hosts the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance where you want to disable AlwaysOn Availability Groups.</span></span>  
  
2.  <span data-ttu-id="f24d8-200">No menu **Iniciar** , aponte para **Todos os Programas**, para [!INCLUDE[ssCurrentUI](../../../includes/sscurrentui-md.md)], para **Ferramentas de Configuração**e clique em **SQL Server Configuration Manager**.</span><span class="sxs-lookup"><span data-stu-id="f24d8-200">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and click **SQL Server Configuration Manager**.</span></span>  
  
3.  <span data-ttu-id="f24d8-201">Em **SQL Server Configuration Manager**, clique em **serviços SQL Server**, clique com o botão direito do mouse em SQL Server (\*\* < *`instance name`*>)\*\*, em que **<*`instance name`*>** é o nome de uma instância de servidor local para a qual você deseja desabilitar grupos de disponibilidade AlwaysOn e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="f24d8-201">In **SQL Server Configuration Manager**, click **SQL Server Services**, right-click SQL Server (**<*`instance name`*>)**, where **<*`instance name`*>** is the name of a local server instance for which you want to disable AlwaysOn Availability Groups, and click **Properties**.</span></span>  
  
4.  <span data-ttu-id="f24d8-202">Na guia**Alta Disponibilidade AlwaysOn**, desmarque a caixa de seleção **Habilitar Grupos de Disponibilidade AlwaysOn** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f24d8-202">On the**AlwaysOn High Availability**tab, deselect the **Enable AlwaysOn Availability Groups** check box, and click **OK**.</span></span>  
  
     [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="f24d8-203">Configuration Manager salvará as alterações e reiniciará o serviço do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f24d8-203">Configuration Manager saves your change and restarts the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service.</span></span> <span data-ttu-id="f24d8-204">Quando o serviço do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] for reiniciado, AlwaysOn será desabilitado e a propriedade de servidor `IsHadrEnabled` será definida como 0 para indicar que os Grupos de Disponibilidade AlwaysOn estão desabilitados.</span><span class="sxs-lookup"><span data-stu-id="f24d8-204">When the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service restarts, AlwaysOn will be disabled, and the `IsHadrEnabled` server property will be set to 0, to indicate that AlwaysOn Availability Groups is disabled.</span></span>  
  
5.  <span data-ttu-id="f24d8-205">Recomendamos que você leia as informações em [Acompanhamento: depois de desabilitar o AlwaysOn](#FollowUp), mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="f24d8-205">We recommend that you read the information in [Follow Up: After Disabling AlwaysOn](#FollowUp), later in this topic.</span></span>  
  
###  <a name="using-sql-server-powershell"></a><a name="PScmd3Procedure"></a> <span data-ttu-id="f24d8-206">Usando o SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="f24d8-206">Using SQL Server PowerShell</span></span>  
 <span data-ttu-id="f24d8-207">**Para desabilitar o AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="f24d8-207">**To disable AlwaysOn**</span></span>  
  
1.  <span data-ttu-id="f24d8-208">Altere o diretório ( `cd` ) para uma instância de servidor habilitada no momento que você deseja desativar para grupos de disponibilidade AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="f24d8-208">Change directory (`cd`) to a currently-enabled server instance that you want to disenable for AlwaysOn Availability Groups.</span></span>  
  
2.  <span data-ttu-id="f24d8-209">Use o cmdlet `Disable-SqlAlwaysOn` para habilitar Grupos de Disponibilidade AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="f24d8-209">Use the `Disable-SqlAlwaysOn` cmdlet to enable AlwaysOn Availability Groups.</span></span>  
  
     <span data-ttu-id="f24d8-210">Por exemplo, o comando a seguir desabilita grupos de disponibilidade AlwaysOn em uma instância de SQL Server (instância de*computador* \\ *Instance*).</span><span class="sxs-lookup"><span data-stu-id="f24d8-210">For example, the following command disables AlwaysOn Availability Groups on an instance of SQL Server (*Computer*\\*Instance*).</span></span>  <span data-ttu-id="f24d8-211">Este comando requer a reinicialização da instância e você será solicitado a confirmar esta reinicialização.</span><span class="sxs-lookup"><span data-stu-id="f24d8-211">This command requires restarting the instance, and you will be prompted to confirm this restart.</span></span>  
  
    ```powershell
    Disable-SqlAlwaysOn -Path SQLSERVER:\SQL\Computer\Instance  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="f24d8-212">Para obter informações sobre como controlar se o `Disable-SqlAlwaysOn` cmdlet reinicia o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] serviço, consulte [quando um cmdlet reinicia o serviço de SQL Server?](#WhenCmdletRestartsSQL), mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="f24d8-212">For information about how to control whether the `Disable-SqlAlwaysOn` cmdlet restarts the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service, see [When Does a Cmdlet Restart the SQL Server Service?](#WhenCmdletRestartsSQL), later in this topic.</span></span>  
  
     <span data-ttu-id="f24d8-213">Para exibir a sintaxe de um cmdlet, use o cmdlet `Get-Help` no ambiente do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f24d8-213">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="f24d8-214">Para obter mais informações, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="f24d8-214">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="f24d8-215">**Para configurar e usar o provedor do SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f24d8-215">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="f24d8-216">Provedor do SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="f24d8-216">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
###  <a name="follow-up-after-disabling-alwayson"></a><a name="FollowUp"></a><span data-ttu-id="f24d8-217">Acompanhamento: depois de desabilitar o AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="f24d8-217">Follow Up: After Disabling AlwaysOn</span></span>  
 <span data-ttu-id="f24d8-218">Depois que você desabilitar os grupos de disponibilidade AlwaysOn, a instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] deverá ser reiniciada.</span><span class="sxs-lookup"><span data-stu-id="f24d8-218">After you disable AlwaysOn Availability Groups, the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] must be restarted.</span></span> <span data-ttu-id="f24d8-219">O SQL Server Configuration Manager reinicia a instância de servidor automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f24d8-219">SQL Configuration Manager restarts the server instance automatically.</span></span> <span data-ttu-id="f24d8-220">Porém, se você usou o cmdlet `Disable-SqlAlwaysOn`, precisará reiniciar a instância de servidor manualmente.</span><span class="sxs-lookup"><span data-stu-id="f24d8-220">However, if you used the `Disable-SqlAlwaysOn` cmdlet, you will need to restart the server instance manually.</span></span> <span data-ttu-id="f24d8-221">Para obter mais informações, consulte [sqlservr Application](../../../tools/sqlservr-application.md).</span><span class="sxs-lookup"><span data-stu-id="f24d8-221">For more information, see [sqlservr Application](../../../tools/sqlservr-application.md).</span></span>  
  
 <span data-ttu-id="f24d8-222">Na instância de servidor reiniciada:</span><span class="sxs-lookup"><span data-stu-id="f24d8-222">On the restarted server instance:</span></span>  
  
-   <span data-ttu-id="f24d8-223">Os bancos de dados de disponibilidade não iniciam na inicialização do SQL Server, tornando-os inacessíveis.</span><span class="sxs-lookup"><span data-stu-id="f24d8-223">Availability databases do not start up at SQL Server startup, making them inaccessible.</span></span>  
  
-   <span data-ttu-id="f24d8-224">A única instrução [!INCLUDE[tsql](../../../includes/tsql-md.md)] AlwaysOn com suporte é [DROP AVAILABILITY GROUP](/sql/t-sql/statements/drop-availability-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f24d8-224">The only supported AlwaysOn [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement is [DROP AVAILABILITY GROUP](/sql/t-sql/statements/drop-availability-group-transact-sql).</span></span> <span data-ttu-id="f24d8-225">CREATE AVAILABILITY GROUP, ALTER AVAILABILITY GROUP e as opções SET HADR de ALTER DATABASE não têm suporte.</span><span class="sxs-lookup"><span data-stu-id="f24d8-225">CREATE AVAILABILITY GROUP, ALTER AVAILABILITY GROUP, and the SET HADR options of ALTER DATABASE are not supported.</span></span>  
  
-   <span data-ttu-id="f24d8-226">Os metadados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e os dados de configuração do [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] no WSFC não são afetados ao desabilitar os Grupos de Disponibilidade AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="f24d8-226">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] metadata and [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] configuration data in WSFC are unaffected by disabling AlwaysOn Availability Groups.</span></span>  
  
 <span data-ttu-id="f24d8-227">Se você desabilitar os grupos de disponibilidade AlwaysOn permanentemente em todas as instâncias de servidor que hospedam uma réplica de disponibilidade para um ou mais grupos de disponibilidade, nós recomendaremos que você conclua as etapas a seguir:</span><span class="sxs-lookup"><span data-stu-id="f24d8-227">If you permanently disable AlwaysOn Availability Groups on every server instance that hosts an availability replica for one or more availability groups, we recommend that you complete the following steps:</span></span>  
  
1.  <span data-ttu-id="f24d8-228">Se você não removeu as réplicas de disponibilidade locais antes de desabilitar o AlwaysOn, exclua (ignore) cada grupo de disponibilidade para o qual a instância de servidor está hospedando uma réplica de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="f24d8-228">If you did not remove the local availability replicas before disabling AlwaysOn, delete (drop) each availability group for which the server instance is hosting an availability replica.</span></span> <span data-ttu-id="f24d8-229">Para obter informações sobre como excluir um grupo de disponibilidade, veja [Remover um grupo de disponibilidade &#40;SQL Server&#41;](remove-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f24d8-229">For information about deleting an availability group, see [Remove an Availability Group &#40;SQL Server&#41;](remove-an-availability-group-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="f24d8-230">Para remover os metadados deixados para trás, exclua (ignore) cada grupo de disponibilidade afetado em uma instância de servidor que faz parte do cluster do WSFC original.</span><span class="sxs-lookup"><span data-stu-id="f24d8-230">To remove the metadata left behind, delete (drop) each affected availability group on a server instance that is part of the original WSFC cluster.</span></span>  
  
3.  <span data-ttu-id="f24d8-231">Qualquer banco de dados primário continuará acessível a todas as conexões, mas a sincronização de dados entre os bancos de dados primário e secundário será interrompida.</span><span class="sxs-lookup"><span data-stu-id="f24d8-231">Any primary databases continue to be accessible to all connections but the data synchronization between the primary and secondary databases stops.</span></span>  
  
4.  <span data-ttu-id="f24d8-232">Os bancos de dados secundários entram no estado RESTORING.</span><span class="sxs-lookup"><span data-stu-id="f24d8-232">The secondary databases enter the RESTORING state.</span></span> <span data-ttu-id="f24d8-233">Você pode excluí-los ou restaurá-los usando RESTORE WITH RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="f24d8-233">You can delete them, or you can restore them by using RESTORE WITH RECOVERY.</span></span> <span data-ttu-id="f24d8-234">No entanto, os bancos de dados restaurados não participarão mais da sincronização de dados de grupos de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="f24d8-234">However, restored databases are no longer participating in availability-group data synchronization.</span></span>  
  
##  <a name="when-does-a-cmdlet-restart-the-sql-server-service"></a><a name="WhenCmdletRestartsSQL"></a> <span data-ttu-id="f24d8-235">Quando um cmdlet reinicia o serviço do SQL Server?</span><span class="sxs-lookup"><span data-stu-id="f24d8-235">When Does a Cmdlet Restart the SQL Server Service?</span></span>  
 <span data-ttu-id="f24d8-236">Em uma instância de servidor atualmente em execução, usando `Enable-SqlAlwaysOn` ou `Disable-SqlAlwaysOn` para alterar a configuração atual de AlwaysOn pode provocar a reinicialização do serviço do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f24d8-236">On a server instance that is currently running, using `Enable-SqlAlwaysOn` or `Disable-SqlAlwaysOn` to change the current AlwaysOn setting could cause the SQL Server service to restart.</span></span> <span data-ttu-id="f24d8-237">O comportamento de reinicialização depende das seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="f24d8-237">The restart behavior on depends on the following conditions:</span></span>  
  
|<span data-ttu-id="f24d8-238">Parâmetro -NoServiceRestart especificado</span><span class="sxs-lookup"><span data-stu-id="f24d8-238">-NoServiceRestart parameter specified</span></span>|<span data-ttu-id="f24d8-239">Parâmetro -Force especificado</span><span class="sxs-lookup"><span data-stu-id="f24d8-239">-Force parameter specified</span></span>|<span data-ttu-id="f24d8-240">O serviço do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] foi reiniciado?</span><span class="sxs-lookup"><span data-stu-id="f24d8-240">Is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service restarted?</span></span>|  
|--------------------------------------------|---------------------------------|---------------------------------------------------------|  
|<span data-ttu-id="f24d8-241">Não</span><span class="sxs-lookup"><span data-stu-id="f24d8-241">No</span></span>|<span data-ttu-id="f24d8-242">Não</span><span class="sxs-lookup"><span data-stu-id="f24d8-242">No</span></span>|<span data-ttu-id="f24d8-243">Por padrão.</span><span class="sxs-lookup"><span data-stu-id="f24d8-243">By default.</span></span> <span data-ttu-id="f24d8-244">Mas o cmdlet solicita o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f24d8-244">But the cmdlet prompts you as follows:</span></span><br /><br /> <span data-ttu-id="f24d8-245">**Para concluir essa ação, devemos reiniciar o serviço SQL Server na instância de servidor “<instance_name>”. Deseja continuar?**</span><span class="sxs-lookup"><span data-stu-id="f24d8-245">**To complete this action, we must restart the SQL Server service for server instance '<instance_name>'. Do you want to continue?**</span></span><br /><br /> <span data-ttu-id="f24d8-246">**[Y] Sim  [N] Não  [S] Suspender  [?] Ajuda (o padrão é “Y”):**</span><span class="sxs-lookup"><span data-stu-id="f24d8-246">**[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):**</span></span><br /><br /> <span data-ttu-id="f24d8-247">Se você especificar **N** ou **S**, o serviço não será reiniciado.</span><span class="sxs-lookup"><span data-stu-id="f24d8-247">If you specify **N** or **S**, the service is not restarted.</span></span>|  
|<span data-ttu-id="f24d8-248">Não</span><span class="sxs-lookup"><span data-stu-id="f24d8-248">No</span></span>|<span data-ttu-id="f24d8-249">Sim</span><span class="sxs-lookup"><span data-stu-id="f24d8-249">Yes</span></span>|<span data-ttu-id="f24d8-250">O serviço será reiniciado.</span><span class="sxs-lookup"><span data-stu-id="f24d8-250">Service is restarted.</span></span>|  
|<span data-ttu-id="f24d8-251">Sim</span><span class="sxs-lookup"><span data-stu-id="f24d8-251">Yes</span></span>|<span data-ttu-id="f24d8-252">Não</span><span class="sxs-lookup"><span data-stu-id="f24d8-252">No</span></span>|<span data-ttu-id="f24d8-253">O serviço não será reiniciado.</span><span class="sxs-lookup"><span data-stu-id="f24d8-253">Service is not restarted.</span></span>|  
|<span data-ttu-id="f24d8-254">Sim</span><span class="sxs-lookup"><span data-stu-id="f24d8-254">Yes</span></span>|<span data-ttu-id="f24d8-255">Sim</span><span class="sxs-lookup"><span data-stu-id="f24d8-255">Yes</span></span>|<span data-ttu-id="f24d8-256">O serviço não será reiniciado.</span><span class="sxs-lookup"><span data-stu-id="f24d8-256">Service is not restarted.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f24d8-257">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f24d8-257">See Also</span></span>  
 <span data-ttu-id="f24d8-258">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f24d8-258">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="f24d8-259">SERVERPROPERTY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f24d8-259">SERVERPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/serverproperty-transact-sql)  
