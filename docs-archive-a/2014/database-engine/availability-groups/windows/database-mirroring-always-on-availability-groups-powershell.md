---
title: Criar um ponto de extremidade de espelhamento de banco de dados para Grupos de Disponibilidade AlwaysOn (SQL Server PowerShell) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], server instance
- Availability Groups [SQL Server], deploying
- Availability Groups [SQL Server], endpoint
ms.assetid: 6197bbe7-67d4-446d-ba5f-cabfa5df77f1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 56058ff8aa72d2471381dd87fb25a3b68356ed36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686362"
---
# <a name="create-a-database-mirroring-endpoint-for-alwayson-availability-groups-sql-server-powershell"></a><span data-ttu-id="9ed63-102">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups (SQL Server PowerShell)</span><span class="sxs-lookup"><span data-stu-id="9ed63-102">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups (SQL Server PowerShell)</span></span>
  <span data-ttu-id="9ed63-103">Este tópico descreve como criar um ponto de extremidade de espelhamento de banco de dados para uso do [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ed63-103">This topic describes how to create a database mirroring endpoint for use by [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using PowerShell.</span></span>  
  
 <span data-ttu-id="9ed63-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="9ed63-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9ed63-105">**Antes de começar:**  [Segurança](#Security)</span><span class="sxs-lookup"><span data-stu-id="9ed63-105">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="9ed63-106">**Para criar um ponto de extremidade de espelhamento de banco de dados usando:**  [PowerShell](#PowerShellProcedure)</span><span class="sxs-lookup"><span data-stu-id="9ed63-106">**To create a database mirroring endpoint, using:**  [PowerShell](#PowerShellProcedure)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="9ed63-107">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="9ed63-107">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9ed63-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="9ed63-108">Security</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9ed63-109">O algoritmo RC4 é preterido.</span><span class="sxs-lookup"><span data-stu-id="9ed63-109">The RC4 algorithm is deprecated.</span></span> [!INCLUDE[ssNoteDepFutureDontUse](../../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="9ed63-110">Recomendamos usar AES.</span><span class="sxs-lookup"><span data-stu-id="9ed63-110">We recommend that you use AES.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9ed63-111">Permissões</span><span class="sxs-lookup"><span data-stu-id="9ed63-111">Permissions</span></span>  
 <span data-ttu-id="9ed63-112">Exige a permissão CREATE ENDPOINT ou a associação na função de servidor fixa sysadmin.</span><span class="sxs-lookup"><span data-stu-id="9ed63-112">Requires CREATE ENDPOINT permission, or membership in the sysadmin fixed server role.</span></span> <span data-ttu-id="9ed63-113">Para obter mais informações, consulte [Permissões GRANT do ponto de extremidade &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9ed63-113">For more information, see [GRANT Endpoint Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql).</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="9ed63-114">Uso do PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ed63-114">Using PowerShell</span></span>  
 <span data-ttu-id="9ed63-115">**Para criar um ponto de extremidade de espelhamento de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="9ed63-115">**To create a database mirroring endpoint**</span></span>  
  
1.  <span data-ttu-id="9ed63-116">Altere o diretório (`cd`) para a instância do servidor para a qual você deseja criar o ponto de extremidade de espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9ed63-116">Change directory (`cd`) to the server instance for which you want to create the database mirroring endpoint.</span></span>  
  
2.  <span data-ttu-id="9ed63-117">Use o cmdlet `New-SqlHadrEndpoint` para criar o ponto de extremidade e use `Set-SqlHadrEndpoint` para iniciar o ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="9ed63-117">Use the `New-SqlHadrEndpoint` cmdlet to create the endpoint and then use the `Set-SqlHadrEndpoint` to start the endpoint.</span></span>  
  
###  <a name="example-powershell"></a><a name="PShellExample"></a> <span data-ttu-id="9ed63-118">Exemplo (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="9ed63-118">Example (PowerShell)</span></span>  
 <span data-ttu-id="9ed63-119">Os comandos do PowerShell a seguir criam um ponto de extremidade de espelhamento de banco de dados em uma instância do SQL Server (instância de*computador* \\ *Instance*).</span><span class="sxs-lookup"><span data-stu-id="9ed63-119">The following PowerShell commands create a database mirroring endpoint on an instance of SQL Server (*Machine*\\*Instance*).</span></span> <span data-ttu-id="9ed63-120">O ponto de extremidade usa a porta 5022.</span><span class="sxs-lookup"><span data-stu-id="9ed63-120">The endpoint uses port 5022.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9ed63-121">Este exemplo só funciona em uma instância de servidor que atualmente não tem um ponto de extremidade de espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9ed63-121">This example works only on a server instance that currently lack a database mirroring endpoint.</span></span>  
  
```powershell
# Create the endpoint.  
$endpoint = New-SqlHadrEndpoint MyMirroringEndpoint -Port 5022 -Path SQLSERVER:\SQL\Machine\Instance  
  
# Start the endpoint  
Set-SqlHadrEndpoint -InputObject $endpoint -State "Started"
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="9ed63-122">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="9ed63-122">Related Tasks</span></span>  
 <span data-ttu-id="9ed63-123">**Para configurar um ponto de extremidade de espelhamento de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="9ed63-123">**To Configure a Database Mirroring Endpoint**</span></span>  
  
-   [<span data-ttu-id="9ed63-124">Criar um ponto de extremidade de espelhamento de banco de dados para a Autenticação do Windows &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9ed63-124">Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md)  
  
-   [<span data-ttu-id="9ed63-125">Usar certificados para um ponto de extremidade de espelhamento de banco de dados &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9ed63-125">Use Certificates for a Database Mirroring Endpoint &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/use-certificates-for-a-database-mirroring-endpoint-transact-sql.md)  
  
    -   [<span data-ttu-id="9ed63-126">Permitir que um ponto de extremidade de espelhamento de banco de dados use certificados para conexões de saída &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9ed63-126">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/database-mirroring-use-certificates-for-outbound-connections.md)  
  
    -   [<span data-ttu-id="9ed63-127">Permitir que um ponto de extremidade de espelhamento de banco de dados use certificados para conexões de entrada &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9ed63-127">Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/database-mirroring-use-certificates-for-inbound-connections.md)  
  
-   [<span data-ttu-id="9ed63-128">Especificar um endereço de rede do servidor &#40;Espelhamento de banco de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="9ed63-128">Specify a Server Network Address &#40;Database Mirroring&#41;</span></span>](../../database-mirroring/specify-a-server-network-address-database-mirroring.md)  
  
-   [<span data-ttu-id="9ed63-129">Especificar a URL do ponto de extremidade ao adicionar ou modificar uma réplica de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9ed63-129">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
 <span data-ttu-id="9ed63-130">**Para exibir informações sobre o ponto de extremidade de espelhamento de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="9ed63-130">**To View Information About the Database Mirroring Endpoint**</span></span>  
  
-   [<span data-ttu-id="9ed63-131">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9ed63-131">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="9ed63-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9ed63-132">See Also</span></span>  
 <span data-ttu-id="9ed63-133">[Criar um grupo de disponibilidade &#40;&#41;Transact-SQL](create-an-availability-group-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="9ed63-133">[Create an Availability Group &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md) </span></span>  
 [<span data-ttu-id="9ed63-134">Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9ed63-134">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
