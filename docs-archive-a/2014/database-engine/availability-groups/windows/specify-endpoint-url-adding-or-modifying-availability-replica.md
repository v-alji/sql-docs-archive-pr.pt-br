---
title: Especifique a URL do ponto de extremidade ao adicionar ou modificar uma réplica de disponibilidade (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- endpoints [SQL Server], AlwaysOn Availability Groups
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], endpoint
- Endpoint URLs (HADR)
ms.assetid: d7520c13-a8ee-4ddc-9e9a-54cd3d27ef1c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: da1eb2bacd4d5a2f7d0b2a623343f62b5e89597d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685295"
---
# <a name="specify-the-endpoint-url-when-adding-or-modifying-an-availability-replica-sql-server"></a><span data-ttu-id="61915-102">Especifique a URL do Ponto de Extremidade Ao Adicionar ou Modificando uma Réplica de disponibilidade (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="61915-102">Specify the Endpoint URL When Adding or Modifying an Availability Replica (SQL Server)</span></span>
  <span data-ttu-id="61915-103">Para hospedar uma réplica de disponibilidade para um grupo de disponibilidade, uma instância de servidor deve ter um ponto de extremidade de espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="61915-103">To host an availability replica for an availability group, a server instance must possess a database mirroring endpoint.</span></span> <span data-ttu-id="61915-104">A instância de servidor usa este ponto de extremidade para escutar mensagens de [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] de réplicas de disponibilidade hospedadas por outras instâncias de servidor.</span><span class="sxs-lookup"><span data-stu-id="61915-104">The server instance uses this endpoint to listen for [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] messages from availability replicas hosted by other server instances.</span></span> <span data-ttu-id="61915-105">Para definir uma réplica de disponibilidade para um grupo de disponibilidade, você deve especificar a URL de ponto de extremidade da instância de servidor que hospedará a réplica.</span><span class="sxs-lookup"><span data-stu-id="61915-105">To define an availability replica for an availability group, you must specify the endpoint URL of the server instance that will host the replica.</span></span> <span data-ttu-id="61915-106">A *URL de ponto de extremidade* identifica o protocolo de transporte do ponto de extremidade de espelhamento de banco de dados – TCP, o endereço do sistema da instância de servidor e o número da porta associado ao ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="61915-106">The *endpoint URL* identifies the transport protocol of the database mirroring endpoint-TCP, the system address of the server instance, and the port number associated with the endpoint.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="61915-107">O termo "URL de ponto de extremidade" é sinônimo do termo "endereço de rede de servidor" usado pela interface do usuário e pela documentação de espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="61915-107">The term "endpoint URL" is synonymous with the term "server network address" used by the database mirroring user interface and documentation.</span></span>  
  
-   [<span data-ttu-id="61915-108">Sintaxe para uma URL de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="61915-108">Syntax for an Endpoint URL</span></span>](#SyntaxOfURL)  
  
-   [<span data-ttu-id="61915-109">Encontrando o nome de domínio totalmente qualificado de um sistema</span><span class="sxs-lookup"><span data-stu-id="61915-109">Finding the Fully Qualified Domain Name of A System</span></span>](#Finding_FQDN)  
  
-   [<span data-ttu-id="61915-110">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="61915-110">Related Tasks</span></span>](#RelatedTasks)  
  
-   [<span data-ttu-id="61915-111">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="61915-111">Related Content</span></span>](#RelatedContent)  
  
##  <a name="syntax-for-an-endpoint-url"></a><a name="SyntaxOfURL"></a> <span data-ttu-id="61915-112">Sintaxe para uma URL de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="61915-112">Syntax for an Endpoint URL</span></span>  
 <span data-ttu-id="61915-113">A sintaxe para uma URL de ponto de extremidade é do seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="61915-113">The syntax for an endpoint URL is of the form:</span></span>  
  
 <span data-ttu-id="61915-114">TCP<strong>://</strong> *\<system-address>* <strong>:</strong> *\<port>*</span><span class="sxs-lookup"><span data-stu-id="61915-114">TCP<strong>://</strong>*\<system-address>*<strong>:</strong>*\<port>*</span></span>  
  
 <span data-ttu-id="61915-115">onde</span><span class="sxs-lookup"><span data-stu-id="61915-115">where</span></span>  
  
-   <span data-ttu-id="61915-116">*\<system-address>* é uma cadeia de caracteres que identifica sem ambiguidade o sistema de computador de destino.</span><span class="sxs-lookup"><span data-stu-id="61915-116">*\<system-address>* is a string that unambiguously identifies the target computer system.</span></span> <span data-ttu-id="61915-117">Normalmente, o endereço de servidor é um nome de sistema (se os sistemas estiverem no mesmo domínio), um nome de domínio completamente qualificado ou um endereço de IP.</span><span class="sxs-lookup"><span data-stu-id="61915-117">Typically, the server address is a system name (if the systems are in the same domain), a fully qualified domain name, or an IP address:</span></span>  
  
    -   <span data-ttu-id="61915-118">Como os nós do cluster WSFC (Windows Server Failover Clustering) são do mesmo domínio, você pode usar o nome do sistema de computador; por exemplo, `SYSTEM46`.</span><span class="sxs-lookup"><span data-stu-id="61915-118">Because the nodes of Windows Server Failover Clustering (WSFC) cluster are the same domain, you can use the name of the computer system; for example, `SYSTEM46`.</span></span>  
  
    -   <span data-ttu-id="61915-119">Para usar um endereço IP, ele deve ser exclusivo em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="61915-119">To use an IP address, it must be unique in your environment.</span></span> <span data-ttu-id="61915-120">Recomendamos que você use um endereço IP somente se ele for estático.</span><span class="sxs-lookup"><span data-stu-id="61915-120">We recommend that you use an IP address only if it is static.</span></span> <span data-ttu-id="61915-121">O endereço IP pode ser o IP Versão 4 (IPv4) ou IP Versão 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="61915-121">The IP address can be IP Version 4 (IPv4) or IP Version 6 (IPv6).</span></span> <span data-ttu-id="61915-122">Um endereço IPv6 deve estar entre colchetes. Por exemplo: **[** _<IPv6_address>_ **]** .</span><span class="sxs-lookup"><span data-stu-id="61915-122">An IPv6 address must be enclosed within square brackets, for example: **[**_<IPv6_address>_**]**.</span></span>  
  
         <span data-ttu-id="61915-123">Para saber o endereço IP de um sistema, no prompt de comando do Windows, digite no comando **ipconfig** .</span><span class="sxs-lookup"><span data-stu-id="61915-123">To learn the IP address of a system, at the Windows command prompt, enter the **ipconfig** command.</span></span>  
  
    -   <span data-ttu-id="61915-124">O nome de domínio completamente qualificado tem seu funcionamento garantido.</span><span class="sxs-lookup"><span data-stu-id="61915-124">The fully qualified domain name is guaranteed to work.</span></span> <span data-ttu-id="61915-125">Esta é uma cadeia de caracteres de endereço definida localmente de formatos diferentes em lugares diferentes.</span><span class="sxs-lookup"><span data-stu-id="61915-125">This is a locally defined address string that takes different forms in different places.</span></span> <span data-ttu-id="61915-126">Frequentemente, mas não sempre, um nome de domínio completamente qualificado é um nome composto que inclui o nome do computador e uma série de segmentos de domínio separados por pontos no formato:</span><span class="sxs-lookup"><span data-stu-id="61915-126">Often, but not always, a fully qualified domain name is a compound name that includes the computer name and a series of period-separated domain segments of the form:</span></span>  
  
         <span data-ttu-id="61915-127">_computer_name_ **.**</span><span class="sxs-lookup"><span data-stu-id="61915-127">_computer_name_ **.**</span></span> <span data-ttu-id="61915-128">_domain_segment_[... **.** _domain_segment_]</span><span class="sxs-lookup"><span data-stu-id="61915-128">_domain_segment_[...**.**_domain_segment_]</span></span>  
  
         <span data-ttu-id="61915-129">em que *computer_name i*é o nome de rede do computador que executa a instância de servidor e *domain_segment*[... **.** _domain_segment_] são as informações restantes de domínio do servidor; por exemplo: `localinfo.corp.Adventure-Works.com`.</span><span class="sxs-lookup"><span data-stu-id="61915-129">where *computer_name i*s the network name of the computer running the server instance, and *domain_segment*[...**.**_domain_segment_] is the remaining domain information of the server; for example: `localinfo.corp.Adventure-Works.com`.</span></span>  
  
         <span data-ttu-id="61915-130">O conteúdo e número de segmentos de domínio são determinados dentro da companhia ou organização.</span><span class="sxs-lookup"><span data-stu-id="61915-130">The content and number of domain segments are determined within the company or organization.</span></span> <span data-ttu-id="61915-131">Para obter mais informações, consulte [Encontrando o nome de domínio completamente qualificado](#Finding_FQDN), posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="61915-131">For more information, see [Finding the Fully Qualified Domain Name](#Finding_FQDN), later in this topic.</span></span>  
  
-   <span data-ttu-id="61915-132">*\<port>* é o número da porta usada pelo ponto de extremidade de espelhamento da instância de servidor parceiro.</span><span class="sxs-lookup"><span data-stu-id="61915-132">*\<port>* is the port number used by the mirroring endpoint of the partner server instance.</span></span>  
  
     <span data-ttu-id="61915-133">Um ponto de extremidade de espelhamento de banco de dados pode usar qualquer porta disponível no sistema do computador.</span><span class="sxs-lookup"><span data-stu-id="61915-133">A database mirroring endpoint can use any available port on the computer system.</span></span> <span data-ttu-id="61915-134">Cada número de porta deve estar associado a somente um ponto de extremidade e cada ponto de extremidade está associado a uma única instância de servidor; e assim, diferentes instâncias de servidor no mesmo servidor escutam em diferentes pontos de extremidade com portas diferentes.</span><span class="sxs-lookup"><span data-stu-id="61915-134">Each port number must be associated with only one endpoint, and each endpoint is associated with a single server instance; thus, different server instances on the same server listen on different endpoints with different ports.</span></span> <span data-ttu-id="61915-135">Por isso, a porta que você especifica na URL de ponto de extremidade quando você especifica uma réplica de disponibilidade sempre direcionará mensagens de entrada para a instância de servidor cujo ponto de extremidade está associado a essa porta.</span><span class="sxs-lookup"><span data-stu-id="61915-135">Therefore, the port you specify in the endpoint URL when you specify an availability replica will always direct incoming messages to the server instance whose endpoint is associated with that port.</span></span>  
  
     <span data-ttu-id="61915-136">Na URL do ponto de extremidade, somente o número da porta identifica a instância de servidor que está associada ao ponto de extremidade de espelhamento no computador de destino.</span><span class="sxs-lookup"><span data-stu-id="61915-136">IIn the endpoint URL, only the number of the port identifies the server instance that is associated with the mirroring endpoint on the target computer.</span></span> <span data-ttu-id="61915-137">A figura a seguir ilustra as URL de ponto de extremidade de duas instâncias de servidor em um único computador.</span><span class="sxs-lookup"><span data-stu-id="61915-137">The following figure illustrates the endpoint URLs of two server instances on a single computer.</span></span> <span data-ttu-id="61915-138">A instância padrão usa a porta `7022` e a instância nomeada usa a porta `7033`.</span><span class="sxs-lookup"><span data-stu-id="61915-138">The default instance uses port `7022` and the named instance uses port `7033`.</span></span> <span data-ttu-id="61915-139">As URLs de ponto de extremidade para estas duas instâncias de servidor são, respectivamente: `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7022` e `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7033`.</span><span class="sxs-lookup"><span data-stu-id="61915-139">The endpoint URL for these two server instances are, respectively: `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7022` and `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7033`.</span></span> <span data-ttu-id="61915-140">Note que o endereço não contém o nome da instância de servidor.</span><span class="sxs-lookup"><span data-stu-id="61915-140">Note that the address does not contain the name of the server instance.</span></span>  
  
     <span data-ttu-id="61915-141">![Endereços de rede de servidor de uma instância padrão](../../media/dbm-2-instances-ports-1-system.gif "Endereços de rede de servidor de uma instância padrão")</span><span class="sxs-lookup"><span data-stu-id="61915-141">![Server network addresses of a default instance](../../media/dbm-2-instances-ports-1-system.gif "Server network addresses of a default instance")</span></span>  
  
     <span data-ttu-id="61915-142">Para identificar a porta associada atualmente com o ponto de extremidade de espelhamento de banco de dados de uma instância de servidor, use a seguinte instrução do [!INCLUDE[tsql](../../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="61915-142">To identify the port currently associated with database mirroring endpoint of a server instance, use the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement:</span></span>  
  
    ```sql
    SELECT type_desc, port FROM sys.TCP_endpoints  
    ```  
  
     <span data-ttu-id="61915-143">Encontre a fila cujo valor **type_desc** é "DATABASE_MIRRORING" e use o número da porta correspondente.</span><span class="sxs-lookup"><span data-stu-id="61915-143">Find the row whose **type_desc** value is "DATABASE_MIRRORING," and use the corresponding port number.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="61915-144">Exemplos</span><span class="sxs-lookup"><span data-stu-id="61915-144">Examples</span></span>  
  
#### <a name="a-using-a-system-name"></a><span data-ttu-id="61915-145">a.</span><span class="sxs-lookup"><span data-stu-id="61915-145">A.</span></span> <span data-ttu-id="61915-146">Usando um nome de sistema</span><span class="sxs-lookup"><span data-stu-id="61915-146">Using a system name</span></span>  
 <span data-ttu-id="61915-147">A URL de ponto de extremidade a seguir especifica um nome de sistema, `SYSTEM46`e a porta `7022`.</span><span class="sxs-lookup"><span data-stu-id="61915-147">The following endpoint URL specifies a system name, `SYSTEM46`, and port `7022`.</span></span>  
  
 `TCP://SYSTEM46:7022`  
  
#### <a name="b-using-a-fully-qualified-domain-name"></a><span data-ttu-id="61915-148">B.</span><span class="sxs-lookup"><span data-stu-id="61915-148">B.</span></span> <span data-ttu-id="61915-149">Usando um nome de domínio completamente qualificado</span><span class="sxs-lookup"><span data-stu-id="61915-149">Using a fully qualified domain name</span></span>  
 <span data-ttu-id="61915-150">A URL de ponto de extremidade a seguir especifica um nome de domínio completamente qualificado, `DBSERVER8.manufacturing.Adventure-Works.com`e a porta `7024`.</span><span class="sxs-lookup"><span data-stu-id="61915-150">The following endpoint URL specifies a fully qualified domain name, `DBSERVER8.manufacturing.Adventure-Works.com`, and port `7024`.</span></span>  
  
 `TCP://DBSERVER8.manufacturing.Adventure-Works.com:7024`  
  
#### <a name="c-using-ipv4"></a><span data-ttu-id="61915-151">C.</span><span class="sxs-lookup"><span data-stu-id="61915-151">C.</span></span> <span data-ttu-id="61915-152">Usando IPv4</span><span class="sxs-lookup"><span data-stu-id="61915-152">Using IPv4</span></span>  
 <span data-ttu-id="61915-153">A URL de ponto de extremidade a seguir especifica um endereço IPv4, `10.193.9.134`e a porta `7023`.</span><span class="sxs-lookup"><span data-stu-id="61915-153">The following endpoint URL specifies an IPv4 address, `10.193.9.134`, and port `7023`.</span></span>  
  
 `TCP://10.193.9.134:7023`  
  
#### <a name="d-using-ipv6"></a><span data-ttu-id="61915-154">D.</span><span class="sxs-lookup"><span data-stu-id="61915-154">D.</span></span> <span data-ttu-id="61915-155">Usando IPv6</span><span class="sxs-lookup"><span data-stu-id="61915-155">Using IPv6</span></span>  
 <span data-ttu-id="61915-156">A URL de ponto de extremidade a seguir contém um endereço IPv6, `2001:4898:23:1002:20f:1fff:feff:b3a3`, e a porta `7022`.</span><span class="sxs-lookup"><span data-stu-id="61915-156">The following endpoint URL contains an IPv6 address, `2001:4898:23:1002:20f:1fff:feff:b3a3`, and port `7022`.</span></span>  
  
 `TCP://[2001:4898:23:1002:20f:1fff:feff:b3a3]:7022`  
  
##  <a name="finding-the-fully-qualified-domain-name-of-a-system"></a><a name="Finding_FQDN"></a> <span data-ttu-id="61915-157">Encontrando o nome de domínio completamente qualificado de um sistema</span><span class="sxs-lookup"><span data-stu-id="61915-157">Finding the Fully Qualified Domain Name of A System</span></span>  
 <span data-ttu-id="61915-158">Para encontrar o nome de domínio completamente qualificado de um sistema, no prompt de comando do Windows desse sistema, digite:</span><span class="sxs-lookup"><span data-stu-id="61915-158">To find the fully qualified domain name of a system, at the Windows command prompt on that system, enter:</span></span>  
  
 <span data-ttu-id="61915-159">**IPCONFIG /ALL**</span><span class="sxs-lookup"><span data-stu-id="61915-159">**IPCONFIG /ALL**</span></span>  
  
 <span data-ttu-id="61915-160">Para formar o nome de domínio totalmente qualificado, concatene os valores de *<host_name>* e *<Primary_Dns_Suffix>* da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="61915-160">To form the fully qualified domain name, concatenate the values of *<host_name>* and *<Primary_Dns_Suffix>* as follows:</span></span>  
  
 <span data-ttu-id="61915-161">_<host_name>_ **.**</span><span class="sxs-lookup"><span data-stu-id="61915-161">_<host_name>_ **.**</span></span> <span data-ttu-id="61915-162">_<Primary_Dns_Suffix>_</span><span class="sxs-lookup"><span data-stu-id="61915-162">_<Primary_Dns_Suffix>_</span></span>  
  
 <span data-ttu-id="61915-163">Por exemplo, a configuração IP</span><span class="sxs-lookup"><span data-stu-id="61915-163">For example, the IP configuration</span></span>  
  
 `Host Name  .  .  .  .  .  .  : MYSERVER`  
  
 `Primary Dns Suffix  .  .  .  : mydomain.Adventure-Works.com`  
  
 <span data-ttu-id="61915-164">se equipara ao nome de domínio completamente qualificado a seguir:</span><span class="sxs-lookup"><span data-stu-id="61915-164">equates to the following fully qualified domain name:</span></span>  
  
 `MYSERVER.mydomain.Adventure-Works.com`  
  
> [!NOTE]  
>  <span data-ttu-id="61915-165">Se você precisar de mais informações sobre um nome de domínio completamente qualificado, consulte seu administrador de sistema.</span><span class="sxs-lookup"><span data-stu-id="61915-165">If you need more information about a fully qualified domain name, see your system administrator.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="61915-166">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="61915-166">Related Tasks</span></span>  
 <span data-ttu-id="61915-167">**Para configurar um ponto de extremidade de espelhamento de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="61915-167">**To Configure a Database Mirroring Endpoint**</span></span>  
  
-   [<span data-ttu-id="61915-168">Criar um ponto de extremidade de espelhamento de banco de dados para Grupos de Disponibilidade AlwaysOn &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="61915-168">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](database-mirroring-always-on-availability-groups-powershell.md)  
  
-   [<span data-ttu-id="61915-169">Criar um ponto de extremidade de espelhamento de banco de dados para a Autenticação do Windows &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="61915-169">Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md)  
  
-   [<span data-ttu-id="61915-170">Usar certificados para um ponto de extremidade de espelhamento de banco de dados &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="61915-170">Use Certificates for a Database Mirroring Endpoint &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/use-certificates-for-a-database-mirroring-endpoint-transact-sql.md)  
  
    -   [<span data-ttu-id="61915-171">Permitir que um ponto de extremidade de espelhamento de banco de dados use certificados para conexões de saída &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="61915-171">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/database-mirroring-use-certificates-for-outbound-connections.md)  
  
    -   [<span data-ttu-id="61915-172">Permitir que um ponto de extremidade de espelhamento de banco de dados use certificados para conexões de entrada &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="61915-172">Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/database-mirroring-use-certificates-for-inbound-connections.md)  
  
-   [<span data-ttu-id="61915-173">Especificar um endereço de rede do servidor &#40;Espelhamento de banco de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="61915-173">Specify a Server Network Address &#40;Database Mirroring&#41;</span></span>](../../database-mirroring/specify-a-server-network-address-database-mirroring.md)  
  
-   [<span data-ttu-id="61915-174">Solucionar problemas de &#40;de configuração de Grupos de Disponibilidade AlwaysOn SQL Server&#41;excluídos</span><span class="sxs-lookup"><span data-stu-id="61915-174">Troubleshoot AlwaysOn Availability Groups Configuration &#40;SQL Server&#41;deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
  
 <span data-ttu-id="61915-175">**Para exibir informações sobre o ponto de extremidade de espelhamento de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="61915-175">**To View Information About the Database Mirroring Endpoint**</span></span>  
  
-   [<span data-ttu-id="61915-176">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="61915-176">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql)  
  
 <span data-ttu-id="61915-177">**Para adicionar uma réplica de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="61915-177">**To add an availability replica**</span></span>  
  
-   [<span data-ttu-id="61915-178">Adicionar uma réplica secundária a um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="61915-178">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="61915-179">Unir uma réplica secundária a um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="61915-179">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="61915-180">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="61915-180">Related Content</span></span>  
  
-   [<span data-ttu-id="61915-181">Guia de soluções AlwaysOn do Microsoft SQL Server para alta disponibilidade e recuperação de desastre</span><span class="sxs-lookup"><span data-stu-id="61915-181">Microsoft SQL Server AlwaysOn Solutions Guide for High Availability and Disaster Recovery</span></span>](https://go.microsoft.com/fwlink/?LinkId=227600)  
  
## <a name="see-also"></a><span data-ttu-id="61915-182">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="61915-182">See Also</span></span>  
 <span data-ttu-id="61915-183">[Criação e configuração de grupos de disponibilidade &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="61915-183">[Creation and Configuration of Availability Groups &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="61915-184">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="61915-184">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="61915-185">CREATE ENDPOINT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="61915-185">CREATE ENDPOINT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-endpoint-transact-sql)  
