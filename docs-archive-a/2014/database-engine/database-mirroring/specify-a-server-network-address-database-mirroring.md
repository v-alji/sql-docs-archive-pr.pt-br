---
title: Especificar um endereço de rede do servidor (espelhamento de banco de dados) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], deployment
- database mirroring [SQL Server], endpoint
- endpoints [SQL Server], database mirroring
- server network addresses [SQL Server]
ms.assetid: a64d4b6b-9016-4f1e-a310-b1df181dd0c6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5c7db7ee6d321229205248059ce09a86f1da101f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574884"
---
# <a name="specify-a-server-network-address-database-mirroring"></a><span data-ttu-id="f6b9f-102">Especificar um endereço de rede do servidor (Espelhamento de banco de dados)</span><span class="sxs-lookup"><span data-stu-id="f6b9f-102">Specify a Server Network Address (Database Mirroring)</span></span>
  <span data-ttu-id="f6b9f-103">A configuração de uma sessão de espelhamento de banco de dados requer um endereço de rede de servidor para cada uma das instâncias de servidor.</span><span class="sxs-lookup"><span data-stu-id="f6b9f-103">Setting up a database mirroring session requires a server network address for each of the server instances.</span></span> <span data-ttu-id="f6b9f-104">O endereço de rede de servidor de uma instância de servidor deve identificar a instância de forma inequívoca fornecendo um endereço de sistema e número de porta na qual a instância está escutando.</span><span class="sxs-lookup"><span data-stu-id="f6b9f-104">The server network address of a server instance must unambiguously identify the instance by providing a system address and the number of the port on which the instance is listening.</span></span>  
  
 <span data-ttu-id="f6b9f-105">Antes de você poder especificar uma porta em um endereço de rede de servidor, deve existir o ponto de extremidade do espelhamento de banco de dados na instância de servidor.</span><span class="sxs-lookup"><span data-stu-id="f6b9f-105">Before you can specify a port in a server network address, the database mirroring endpoint must exist on the server instance.</span></span> <span data-ttu-id="f6b9f-106">Para obter mais informações, veja [Criar um ponto de extremidade de espelhamento de banco de dados para a Autenticação do Windows &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="f6b9f-106">For more information, see [Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span></span>  
  
  
  
##  <a name="syntax-for-a-server-network-address"></a><a name="Syntax"></a> <span data-ttu-id="f6b9f-107">Sintaxe para um endereço de rede de servidor</span><span class="sxs-lookup"><span data-stu-id="f6b9f-107">Syntax for a Server Network Address</span></span>  
 <span data-ttu-id="f6b9f-108">A sintaxe para um endereço de rede de servidor é do formato:</span><span class="sxs-lookup"><span data-stu-id="f6b9f-108">The syntax for a server network address is of the form:</span></span>  
  
 <span data-ttu-id="f6b9f-109">TCP<strong>://</strong> *\<system-address>* <strong> :<strong>*\<port>*</span><span class="sxs-lookup"><span data-stu-id="f6b9f-109">TCP<strong>://</strong>*\<system-address>*<strong>:<strong>*\<port>*</span></span> 
  
 <span data-ttu-id="f6b9f-110">onde</span><span class="sxs-lookup"><span data-stu-id="f6b9f-110">where</span></span>  
  
-   <span data-ttu-id="f6b9f-111">*\<system-address>* é uma cadeia de caracteres que identifica sem ambiguidade o sistema de computador de destino.</span><span class="sxs-lookup"><span data-stu-id="f6b9f-111">*\<system-address>* is a string that unambiguously identifies the destination computer system.</span></span> <span data-ttu-id="f6b9f-112">Normalmente, o endereço de servidor é um nome de sistema (se os sistemas estiverem no mesmo domínio), um nome de domínio completamente qualificado ou um endereço de IP.</span><span class="sxs-lookup"><span data-stu-id="f6b9f-112">Typically, the server address is a system name (if the systems are in the same domain), a fully qualified domain name, or an IP address:</span></span>  
  
    -   <span data-ttu-id="f6b9f-113">Se os sistemas estiverem no mesmo domínio, você poderá usar o nome do sistema de computador; por exemplo, `SYSTEM46`.</span><span class="sxs-lookup"><span data-stu-id="f6b9f-113">If the systems are the same domain, you can use the name of the computer system; for example, `SYSTEM46`.</span></span>  
  
    -   <span data-ttu-id="f6b9f-114">Para usar um endereço IP, ele deve ser exclusivo em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="f6b9f-114">To use an IP address, it must be unique in your environment.</span></span> <span data-ttu-id="f6b9f-115">Recomendamos que você use um endereço IP somente se ele for estático.</span><span class="sxs-lookup"><span data-stu-id="f6b9f-115">We recommend that you use an IP address only if it is static.</span></span> <span data-ttu-id="f6b9f-116">O endereço IP pode ser o IP Versão 4 (IPv4) ou IP Versão 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="f6b9f-116">The IP address can be IP Version 4 (IPv4) or IP Version 6 (IPv6).</span></span> <span data-ttu-id="f6b9f-117">Um endereço IPv6 deve estar entre colchetes. Por exemplo: **[** _<IPv6_address>_ **]** .</span><span class="sxs-lookup"><span data-stu-id="f6b9f-117">An IPv6 address must be enclosed within square brackets, for example: **[**_<IPv6_address>_**]**.</span></span>  
  
         <span data-ttu-id="f6b9f-118">Para saber o endereço IP de um sistema, no prompt de comando do Windows, digite no comando **ipconfig** .</span><span class="sxs-lookup"><span data-stu-id="f6b9f-118">To learn the IP address of a system, at the Windows command prompt, enter the **ipconfig** command.</span></span>  
  
    -   <span data-ttu-id="f6b9f-119">O nome de domínio completamente qualificado tem seu funcionamento garantido.</span><span class="sxs-lookup"><span data-stu-id="f6b9f-119">The fully qualified domain name is guaranteed to work.</span></span> <span data-ttu-id="f6b9f-120">Esta é uma cadeia de caracteres de endereço definida localmente de formatos diferentes em lugares diferentes.</span><span class="sxs-lookup"><span data-stu-id="f6b9f-120">This is a locally defined address string that different forms in different places.</span></span> <span data-ttu-id="f6b9f-121">Frequentemente, mas não sempre, um nome de domínio completamente qualificado é um nome composto que inclui o nome do computador e uma série de segmentos de domínio separados por pontos no formato:</span><span class="sxs-lookup"><span data-stu-id="f6b9f-121">Often, but not always, a fully qualified domain name is a compound name that includes the computer name and a series of period-separated domain segments of the form:</span></span>  
  
         <span data-ttu-id="f6b9f-122">_computer_name_ **.**</span><span class="sxs-lookup"><span data-stu-id="f6b9f-122">_computer_name_ **.**</span></span> <span data-ttu-id="f6b9f-123">_domain_segment_[... **.** _domain_segment_]</span><span class="sxs-lookup"><span data-stu-id="f6b9f-123">_domain_segment_[...**.**_domain_segment_]</span></span>  
  
         <span data-ttu-id="f6b9f-124">em que *computer_name i*é o nome de rede do computador que executa a instância de servidor e *domain_segment*[... **.** _domain_segment_] são as informações restantes de domínio do servidor; por exemplo: `localinfo.corp.Adventure-Works.com`.</span><span class="sxs-lookup"><span data-stu-id="f6b9f-124">where *computer_name i*s the network name of the computer running the server instance, and *domain_segment*[...**.**_domain_segment_] is the remaining domain information of the server; for example: `localinfo.corp.Adventure-Works.com`.</span></span>  
  
         <span data-ttu-id="f6b9f-125">O conteúdo e número de segmentos de domínio são determinados dentro da companhia ou organização.</span><span class="sxs-lookup"><span data-stu-id="f6b9f-125">The content and number of domain segments are determined within the company or organization.</span></span> <span data-ttu-id="f6b9f-126">Se você não conhecer o nome de domínio completamente qualificado do seu servidor, consulte seu administrador de sistema.</span><span class="sxs-lookup"><span data-stu-id="f6b9f-126">If you do not know the fully qualified domain name for your server, see your system administrator.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="f6b9f-127">Para obter informações sobre como achar um nome de domínio completamente qualificado, consulte "Encontrando o nome de domínio completamente qualificado", mais abaixo neste tópico.</span><span class="sxs-lookup"><span data-stu-id="f6b9f-127">For information about how to find a fully qualified domain name, see "Finding the Fully Qualified Domain Name," later in this topic.</span></span>  
  
-   <span data-ttu-id="f6b9f-128">*\<port>* é o número da porta usada pelo ponto de extremidade de espelhamento da instância de servidor parceiro.</span><span class="sxs-lookup"><span data-stu-id="f6b9f-128">*\<port>* is the port number used by the mirroring endpoint of the partner server instance.</span></span> <span data-ttu-id="f6b9f-129">Para obter informações sobre como especificar um ponto de extremidade, veja [Criar um ponto de extremidade de espelhamento de banco de dados para a Autenticação do Windows &#40;SQL Server&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="f6b9f-129">For information about specifying an endpoint, see [Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span></span>  
  
     <span data-ttu-id="f6b9f-130">Um ponto de extremidade de espelhamento de banco de dados pode usar qualquer porta disponível no sistema do computador.</span><span class="sxs-lookup"><span data-stu-id="f6b9f-130">A database mirroring endpoint can use any available port on the computer system.</span></span> <span data-ttu-id="f6b9f-131">Cada número de porta em um sistema de computador deve estar associado a somente um ponto de extremidade e cada ponto de extremidade está associado a uma única instância de servidor; e assim, diferentes instâncias de servidor no mesmo servidor escutam em diferentes pontos de extremidade com portas diferentes.</span><span class="sxs-lookup"><span data-stu-id="f6b9f-131">Each port number on a computer system must be associated with only one endpoint, and each endpoint is associated with a single server instance; thus, different server instances on the same server listen on different endpoints with different ports.</span></span> <span data-ttu-id="f6b9f-132">Por isso, a porta que você especifica no endereço de rede de servidor quando você configura uma sessão de espelhamento de banco de dados sempre dirigirá a sessão à instância de servidor cujo ponto de extremidade está associado a essa porta.</span><span class="sxs-lookup"><span data-stu-id="f6b9f-132">Therefore, the port you specify in the server network address when you set up a database mirroring session will always direct the session to the server instance whose endpoint is associated with that port.</span></span>  
  
     <span data-ttu-id="f6b9f-133">No endereço de rede de servidor de uma instância de servidor, somente o número da porta associado a seu ponto de extremidade de espelhamento distingue essa instância de qualquer outra instância no computador.</span><span class="sxs-lookup"><span data-stu-id="f6b9f-133">In the server network address of a server instance, only the number of the port associated with its mirroring endpoint distinguishes that instance from any other instances on the computer.</span></span> <span data-ttu-id="f6b9f-134">A figura a seguir ilustra os endereços de rede de servidor de duas instâncias de servidor em um único computador.</span><span class="sxs-lookup"><span data-stu-id="f6b9f-134">The following figure illustrates the server network addresses of two server instances on a single computer.</span></span> <span data-ttu-id="f6b9f-135">A instância padrão usa a porta `7022` e a instância nomeada usa a porta `7033`.</span><span class="sxs-lookup"><span data-stu-id="f6b9f-135">The default instance uses port `7022` and the named instance uses port `7033`.</span></span> <span data-ttu-id="f6b9f-136">O endereço de rede de servidor para estas duas instâncias de servidor é, respectivamente: `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7022` e `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7033`.</span><span class="sxs-lookup"><span data-stu-id="f6b9f-136">The server network address for these two server instances are, respectively: `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7022` and `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7033`.</span></span> <span data-ttu-id="f6b9f-137">Note que o endereço não contém o nome da instância de servidor.</span><span class="sxs-lookup"><span data-stu-id="f6b9f-137">Note that the address does not contain the name of the server instance.</span></span>  
  
     <span data-ttu-id="f6b9f-138">![Endereços de rede de servidor de uma instância padrão](../media/dbm-2-instances-ports-1-system.gif "Endereços de rede de servidor de uma instância padrão")</span><span class="sxs-lookup"><span data-stu-id="f6b9f-138">![Server network addresses of a default instance](../media/dbm-2-instances-ports-1-system.gif "Server network addresses of a default instance")</span></span>  
  
     <span data-ttu-id="f6b9f-139">Para identificar a porta associada atualmente com o ponto de extremidade de espelhamento de banco de dados de uma instância de servidor, use a seguinte instrução do [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="f6b9f-139">To identify the port currently associated with database mirroring endpoint of a server instance, use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```  
    SELECT type_desc, port FROM sys.tcp_endpoints  
    ```  
  
     <span data-ttu-id="f6b9f-140">Encontre a fila cujo valor **type_desc** é "DATABASE_MIRRORING" e use o número da porta correspondente.</span><span class="sxs-lookup"><span data-stu-id="f6b9f-140">Find the row whose **type_desc** value is "DATABASE_MIRRORING," and use the corresponding port number.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="f6b9f-141">Exemplos</span><span class="sxs-lookup"><span data-stu-id="f6b9f-141">Examples</span></span>  
  
#### <a name="a-using-a-system-name"></a><span data-ttu-id="f6b9f-142">a.</span><span class="sxs-lookup"><span data-stu-id="f6b9f-142">A.</span></span> <span data-ttu-id="f6b9f-143">Usando um nome de sistema</span><span class="sxs-lookup"><span data-stu-id="f6b9f-143">Using a system name</span></span>  
 <span data-ttu-id="f6b9f-144">O endereço de rede de servidor a seguir especifica um nome de sistema, `SYSTEM46`e a porta `7022`.</span><span class="sxs-lookup"><span data-stu-id="f6b9f-144">The following server network address specifies a system name, `SYSTEM46`, and port `7022`.</span></span>  
  
```  
ALTER DATABASE AdventureWorks SET PARTNER ='tcp://SYSTEM46:7022';  
```  
  
#### <a name="b-using-a-fully-qualified-domain-name"></a><span data-ttu-id="f6b9f-145">B.</span><span class="sxs-lookup"><span data-stu-id="f6b9f-145">B.</span></span> <span data-ttu-id="f6b9f-146">Usando um nome de domínio completamente qualificado</span><span class="sxs-lookup"><span data-stu-id="f6b9f-146">Using a fully qualified domain name</span></span>  
 <span data-ttu-id="f6b9f-147">O endereço de rede de servidor a seguir especifica um nome de domínio completamente qualificado, `DBSERVER8.manufacturing.Adventure-Works.com`e a porta `7024`.</span><span class="sxs-lookup"><span data-stu-id="f6b9f-147">The following server network address specifies a fully qualified domain name, `DBSERVER8.manufacturing.Adventure-Works.com`, and port `7024`.</span></span>  
  
```  
ALTER DATABASE AdventureWorks SET PARTNER ='tcp://DBSERVER8.manufacturing.Adventure-Works.com:7024';  
```  
  
#### <a name="c-using-ipv4"></a><span data-ttu-id="f6b9f-148">C.</span><span class="sxs-lookup"><span data-stu-id="f6b9f-148">C.</span></span> <span data-ttu-id="f6b9f-149">Usando IPv4</span><span class="sxs-lookup"><span data-stu-id="f6b9f-149">Using IPv4</span></span>  
 <span data-ttu-id="f6b9f-150">O endereço de rede de servidor a seguir especifica um endereço IPv4, `10.193.9.134`e a porta `7023`.</span><span class="sxs-lookup"><span data-stu-id="f6b9f-150">The following server network address specifies an IPv4 address, `10.193.9.134`, and port `7023`.</span></span>  
  
```  
ALTER DATABASE AdventureWorks SET PARTNER ='tcp://10.193.9.134:7023';  
```  
  
#### <a name="d-using-ipv6"></a><span data-ttu-id="f6b9f-151">D.</span><span class="sxs-lookup"><span data-stu-id="f6b9f-151">D.</span></span> <span data-ttu-id="f6b9f-152">Usando IPv6</span><span class="sxs-lookup"><span data-stu-id="f6b9f-152">Using IPv6</span></span>  
 <span data-ttu-id="f6b9f-153">O endereço de servidor de rede a seguir contém um endereço IPv6, `2001:4898:23:1002:20f:1fff:feff:b3a3`, e a porta `7022`.</span><span class="sxs-lookup"><span data-stu-id="f6b9f-153">The following server network address contains an IPv6 address, `2001:4898:23:1002:20f:1fff:feff:b3a3`, and port `7022`.</span></span>  
  
```  
ALTER DATABASE AdventureWorks SET PARTNER ='tcp://[2001:4898:23:1002:20f:1fff:feff:b3a3]:7022';  
```  
  
## <a name="finding-the-fully-qualified-domain-name"></a><span data-ttu-id="f6b9f-154">B. Encontrando o nome de domínio completamente qualificado</span><span class="sxs-lookup"><span data-stu-id="f6b9f-154">Finding the Fully Qualified Domain Name</span></span>  
 <span data-ttu-id="f6b9f-155">Para encontrar o nome de domínio completamente qualificado de um sistema, no prompt de comando do Windows desse sistema, digite:</span><span class="sxs-lookup"><span data-stu-id="f6b9f-155">To find the fully qualified domain name of a system, at the Windows command prompt on that system, enter:</span></span>  
  
 <span data-ttu-id="f6b9f-156">**IPCONFIG /ALL**</span><span class="sxs-lookup"><span data-stu-id="f6b9f-156">**IPCONFIG /ALL**</span></span>  
  
 <span data-ttu-id="f6b9f-157">Para formar o nome de domínio totalmente qualificado, concatene os valores de *<host_name>* e *<Primary_Dns_Suffix>* da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="f6b9f-157">To form the fully qualified domain name, concatenate the values of *<host_name>* and *<Primary_Dns_Suffix>* as follows:</span></span>  
  
 <span data-ttu-id="f6b9f-158">_<host_name>_ **.**</span><span class="sxs-lookup"><span data-stu-id="f6b9f-158">_<host_name>_ **.**</span></span> <span data-ttu-id="f6b9f-159">_<Primary_Dns_Suffix>_</span><span class="sxs-lookup"><span data-stu-id="f6b9f-159">_<Primary_Dns_Suffix>_</span></span>  
  
 <span data-ttu-id="f6b9f-160">Por exemplo, a configuração IP</span><span class="sxs-lookup"><span data-stu-id="f6b9f-160">For example, the IP configuration</span></span>  
  
 `Host Name  .  .  .  .  .  .  : MYSERVER`  
  
 `Primary Dns Suffix  .  .  .  : mydomain.Adventure-Works.com`  
  
 <span data-ttu-id="f6b9f-161">se equipara ao nome de domínio completamente qualificado a seguir:</span><span class="sxs-lookup"><span data-stu-id="f6b9f-161">equates to the following fully qualified domain name:</span></span>  
  
 `MYSERVER.mydomain.Adventure-Works.com`  
  
##  <a name="examples"></a><a name="Examples"></a> <span data-ttu-id="f6b9f-162">Exemplos</span><span class="sxs-lookup"><span data-stu-id="f6b9f-162">Examples</span></span>  
 <span data-ttu-id="f6b9f-163">O exemplo a seguir mostra o endereço de rede de servidor para uma instância de servidor em um sistema de computador nomeado `REMOTESYSTEM3` em outro domínio.</span><span class="sxs-lookup"><span data-stu-id="f6b9f-163">The following example shows the server network address for a server instance on a computer system named `REMOTESYSTEM3` in another domain.</span></span> <span data-ttu-id="f6b9f-164">As informações de domínio são `NORTHWEST.ADVENTURE-WORKS.COM`e a porta do ponto de extremidade de espelhamento de banco de dados é `7025`.</span><span class="sxs-lookup"><span data-stu-id="f6b9f-164">The domain information is `NORTHWEST.ADVENTURE-WORKS.COM`, and the port of the database mirroring endpoint is `7025`.</span></span> <span data-ttu-id="f6b9f-165">Tendo estes exemplos de componentes determinados, o endereço de rede de servidor é.</span><span class="sxs-lookup"><span data-stu-id="f6b9f-165">Given these example components, the server network address is.</span></span>  
  
 `TCP://REMOTESYSTEM3.NORTHWEST.ADVENTURE-WORKS.COM:7025`  
  
 <span data-ttu-id="f6b9f-166">O exemplo a seguir exibe o endereço de rede de servidor para uma instância de servidor em um sistema de computador nomeado `DBSERVER1`.</span><span class="sxs-lookup"><span data-stu-id="f6b9f-166">The following example shows the server network address for a server instance on a computer system named `DBSERVER1`.</span></span> <span data-ttu-id="f6b9f-167">Este sistema está no domínio local e é identificado sem-ambiguidade por seu nome de sistema.</span><span class="sxs-lookup"><span data-stu-id="f6b9f-167">This system is in the local domain and is unambiguously identified by its system name.</span></span> <span data-ttu-id="f6b9f-168">A porta do ponto de extremidade de espelhamento de banco de dados é `7022`.</span><span class="sxs-lookup"><span data-stu-id="f6b9f-168">The port of the database mirroring endpoint is `7022`.</span></span>  
  
 `TCP://DBSERVER1:7022`  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="f6b9f-169">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="f6b9f-169">Related Tasks</span></span>  
  
-   [<span data-ttu-id="f6b9f-170">Criar um ponto de extremidade de espelhamento de banco de dados para a Autenticação do Windows &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f6b9f-170">Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;</span></span>](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="f6b9f-171">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f6b9f-171">See Also</span></span>  
 <span data-ttu-id="f6b9f-172">[Espelhamento de banco de dados &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f6b9f-172">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="f6b9f-173">O ponto de extremidade de espelhamento de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f6b9f-173">The Database Mirroring Endpoint &#40;SQL Server&#41;</span></span>](the-database-mirroring-endpoint-sql-server.md)  
  
  
