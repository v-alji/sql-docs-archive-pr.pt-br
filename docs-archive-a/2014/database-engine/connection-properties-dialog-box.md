---
title: Caixa de diálogo Propriedades da Conexão | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connectionproperties.f1
helpviewer_keywords:
- Connection Properties dialog box
ms.assetid: 6df812ad-4d80-4503-8a23-47719ce85624
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: db2817ebaf3f1655f146c060fcb79d550ad0cc8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684869"
---
# <a name="connection-properties-dialog-box"></a><span data-ttu-id="8310f-102">caixa de diálogo Propriedades da conexão</span><span class="sxs-lookup"><span data-stu-id="8310f-102">Connection Properties Dialog Box</span></span>
  <span data-ttu-id="8310f-103">Use essa caixa de diálogo para exibir as propriedades da conexão atual.</span><span class="sxs-lookup"><span data-stu-id="8310f-103">Use this dialog box to view the current connection properties.</span></span> <span data-ttu-id="8310f-104">Essa caixa de diálogo está disponível quando você clica em **Exibir propriedades da conexão** em várias caixas de diálogo do Pesquisador de Objetos.</span><span class="sxs-lookup"><span data-stu-id="8310f-104">This dialog box is available when you click **View connection properties** in various Object Explorer dialog boxes.</span></span> <span data-ttu-id="8310f-105">As propriedades exibidas nessa página são somente leitura.</span><span class="sxs-lookup"><span data-stu-id="8310f-105">The properties displayed on this page are read-only.</span></span>  
  
 <span data-ttu-id="8310f-106">Para alterar propriedades como **Banco de Dados**, conecte ao banco de dados desejado com o Pesquisador de Objetos antes de abrir a caixa de diálogo **Propriedades da Conexão** .</span><span class="sxs-lookup"><span data-stu-id="8310f-106">To change properties such as **Database**, connect to the desired database with Object Explorer before opening the **Connection Properties** dialog box.</span></span>  
  
 <span data-ttu-id="8310f-107">Observe que o período limite de consulta para o SQL Azure é de 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="8310f-107">Note that the query time-out period for SQL Azure is 30 minutes.</span></span>  
  
## <a name="authentication"></a><span data-ttu-id="8310f-108">Autenticação</span><span class="sxs-lookup"><span data-stu-id="8310f-108">Authentication</span></span>  
 <span data-ttu-id="8310f-109">Exiba propriedades de autenticação para a conexão atual.</span><span class="sxs-lookup"><span data-stu-id="8310f-109">View authentication properties for the current connection.</span></span> <span data-ttu-id="8310f-110">As propriedades de autenticação são o logon e método de autenticação quando a conexão foi estabelecida.</span><span class="sxs-lookup"><span data-stu-id="8310f-110">Authentication properties are the login and authentication method when the connection was established.</span></span> <span data-ttu-id="8310f-111">Para alterar as propriedades de autenticação, desconectar de [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e, em seguida, conectar o pesquisador de objetos ao servidor novamente, usando as opções de conexão desejadas.</span><span class="sxs-lookup"><span data-stu-id="8310f-111">To change the authentication properties, disconnect from [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], and then connect Object Explorer to the server again, using the desired connection options.</span></span>  
  
 <span data-ttu-id="8310f-112">**Método de autenticação**</span><span class="sxs-lookup"><span data-stu-id="8310f-112">**Authentication Method**</span></span>  
 <span data-ttu-id="8310f-113">O método de autenticação usado para a conexão atual.</span><span class="sxs-lookup"><span data-stu-id="8310f-113">The authentication method used for the current connection.</span></span>  
  
 <span data-ttu-id="8310f-114">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="8310f-114">**User Name**</span></span>  
 <span data-ttu-id="8310f-115">O nome do usuário de logon usado para a autenticação da conexão.</span><span class="sxs-lookup"><span data-stu-id="8310f-115">The name of the user of login used for the connection authentication.</span></span>  
  
## <a name="connection-category"></a><span data-ttu-id="8310f-116">Categoria de conexão</span><span class="sxs-lookup"><span data-stu-id="8310f-116">Connection Category</span></span>  
 <span data-ttu-id="8310f-117">Exiba as propriedades de conexão para a conexão atual.</span><span class="sxs-lookup"><span data-stu-id="8310f-117">View connection properties for the current connection.</span></span> <span data-ttu-id="8310f-118">A maioria das propriedades da conexão foi selecionada na guia **Propriedades da Conexão** da caixa de diálogo **Conectar ao servidor** durante o processo de conexão.</span><span class="sxs-lookup"><span data-stu-id="8310f-118">Most connection properties were selected on the **Connection Properties** tab of the **Connect to server** dialog box during the connection process.</span></span>  
  
 <span data-ttu-id="8310f-119">**Backup de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="8310f-119">**Database**</span></span>  
 <span data-ttu-id="8310f-120">O nome do banco de dados ao qual se está conectado atualmente.</span><span class="sxs-lookup"><span data-stu-id="8310f-120">The name of the database currently connected to.</span></span> <span data-ttu-id="8310f-121">Para alterar isso, use a barra de ferramentas do SQL Editor.</span><span class="sxs-lookup"><span data-stu-id="8310f-121">To change this use, the SQL Editor toolbar.</span></span>  
  
 <span data-ttu-id="8310f-122">**SPID**</span><span class="sxs-lookup"><span data-stu-id="8310f-122">**SPID**</span></span>  
 <span data-ttu-id="8310f-123">A ID do processo do sistema atribuída pelo servidor à conexão.</span><span class="sxs-lookup"><span data-stu-id="8310f-123">The system process ID assigned by the server to the connection.</span></span> <span data-ttu-id="8310f-124">Isso não pode ser alterado para essa conexão.</span><span class="sxs-lookup"><span data-stu-id="8310f-124">This cannot be changed for this connection.</span></span>  
  
 <span data-ttu-id="8310f-125">**Protocolo de rede**</span><span class="sxs-lookup"><span data-stu-id="8310f-125">**Network Protocol**</span></span>  
 <span data-ttu-id="8310f-126">O protocolo de rede da conexão do [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8310f-126">The network protocol of the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] connection.</span></span> <span data-ttu-id="8310f-127">Para alterar isso, conecte novamente com as propriedades de conexão desejadas.</span><span class="sxs-lookup"><span data-stu-id="8310f-127">To change this, connect again with the desired connection properties.</span></span>  
  
 <span data-ttu-id="8310f-128">**Tamanho do Pacote de Rede**</span><span class="sxs-lookup"><span data-stu-id="8310f-128">**Network Packet Size**</span></span>  
 <span data-ttu-id="8310f-129">O tamanho de pacote usado ao comunicar com o servidor.</span><span class="sxs-lookup"><span data-stu-id="8310f-129">The packet size used when communicating with the server.</span></span> <span data-ttu-id="8310f-130">Para alterar isso, conecte novamente com as propriedades de conexão desejadas.</span><span class="sxs-lookup"><span data-stu-id="8310f-130">To change this, connect again with the desired connection properties.</span></span>  
  
 <span data-ttu-id="8310f-131">**Tempo limite da conexão**</span><span class="sxs-lookup"><span data-stu-id="8310f-131">**Connection Timeout**</span></span>  
 <span data-ttu-id="8310f-132">O intervalo de tempo em segundos a esperar quando conectar ao [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] antes de atingir o tempo-limite e retornar ao usuário uma falha em conectar.</span><span class="sxs-lookup"><span data-stu-id="8310f-132">The amount of time is seconds to wait when connecting to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] before timing out and returning a failure to connect error to the user.</span></span> <span data-ttu-id="8310f-133">Para alterar isso, conecte novamente com as propriedades de conexão desejadas.</span><span class="sxs-lookup"><span data-stu-id="8310f-133">To change this, connect again with the desired connection properties.</span></span>  
  
 <span data-ttu-id="8310f-134">**Tempo limite de execução**</span><span class="sxs-lookup"><span data-stu-id="8310f-134">**Execution Timeout**</span></span>  
 <span data-ttu-id="8310f-135">O intervalo de tempo em segundos a aguardar antes que a execução de uma tarefa seja concluída no servidor.</span><span class="sxs-lookup"><span data-stu-id="8310f-135">The amount of time in seconds to wait before execution of a task is completed on the server.</span></span> <span data-ttu-id="8310f-136">Para alterar isso, conecte novamente com as propriedades de conexão desejadas.</span><span class="sxs-lookup"><span data-stu-id="8310f-136">To change this, connect again with the desired connection properties.</span></span>  
  
 <span data-ttu-id="8310f-137">**Criptografado**</span><span class="sxs-lookup"><span data-stu-id="8310f-137">**Encrypted**</span></span>  
 <span data-ttu-id="8310f-138">Se a conexão atual é criptografada.</span><span class="sxs-lookup"><span data-stu-id="8310f-138">Whether the current connection is encrypted.</span></span> <span data-ttu-id="8310f-139">Para alterar isso, conecte novamente com as propriedades de conexão desejadas.</span><span class="sxs-lookup"><span data-stu-id="8310f-139">To change this, connect again with the desired connection properties.</span></span>  
  
## <a name="product-category"></a><span data-ttu-id="8310f-140">Categoria do Produto</span><span class="sxs-lookup"><span data-stu-id="8310f-140">Product Category</span></span>  
 <span data-ttu-id="8310f-141">Exiba as propriedades do produto para a conexão atual.</span><span class="sxs-lookup"><span data-stu-id="8310f-141">View product properties for the current connection.</span></span> <span data-ttu-id="8310f-142">Essas propriedades descrevem o produto de servidor, versão, nome de instância e ordenação.</span><span class="sxs-lookup"><span data-stu-id="8310f-142">These properties describe the server product, version, instance name, and collation.</span></span> <span data-ttu-id="8310f-143">As propriedades são definidas durante a instalação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8310f-143">The properties are set during [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] installation.</span></span>  
  
 <span data-ttu-id="8310f-144">**Nome do produto**</span><span class="sxs-lookup"><span data-stu-id="8310f-144">**Product Name**</span></span>  
 <span data-ttu-id="8310f-145">O nome do produto do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8310f-145">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] product name.</span></span>  
  
 <span data-ttu-id="8310f-146">**Versão do produto**</span><span class="sxs-lookup"><span data-stu-id="8310f-146">**Product Version**</span></span>  
 <span data-ttu-id="8310f-147">A versão do produto do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8310f-147">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] product version.</span></span>  
  
 <span data-ttu-id="8310f-148">**Nome do servidor**</span><span class="sxs-lookup"><span data-stu-id="8310f-148">**Server Name**</span></span>  
 <span data-ttu-id="8310f-149">O nome do computador que executa o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8310f-149">The name of the computer running [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="8310f-150">**Nome da instância**</span><span class="sxs-lookup"><span data-stu-id="8310f-150">**Instance Name**</span></span>  
 <span data-ttu-id="8310f-151">Nome da instância do servidor.</span><span class="sxs-lookup"><span data-stu-id="8310f-151">The instance name of the server.</span></span> <span data-ttu-id="8310f-152">A instância padrão é em branco.</span><span class="sxs-lookup"><span data-stu-id="8310f-152">The default instance is blank.</span></span>  
  
 <span data-ttu-id="8310f-153">**Idioma**</span><span class="sxs-lookup"><span data-stu-id="8310f-153">**Language**</span></span>  
 <span data-ttu-id="8310f-154">A versão do idioma do produto do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8310f-154">The language version of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] product.</span></span>  
  
 <span data-ttu-id="8310f-155">**Ordenação**</span><span class="sxs-lookup"><span data-stu-id="8310f-155">**Collation**</span></span>  
 <span data-ttu-id="8310f-156">A ordenação do servidor.</span><span class="sxs-lookup"><span data-stu-id="8310f-156">The collation of the server.</span></span>  
  
## <a name="server-environment-category"></a><span data-ttu-id="8310f-157">Categoria do ambiente do servidor</span><span class="sxs-lookup"><span data-stu-id="8310f-157">Server Environment Category</span></span>  
 <span data-ttu-id="8310f-158">Exiba propriedades do ambiente do servidor para a conexão atual relacionadas ao hardware do servidor e sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="8310f-158">View server environment properties for the current connection related to the server hardware and operating system.</span></span> <span data-ttu-id="8310f-159">As propriedades não podem ser configuradas pelo [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8310f-159">The properties cannot be configured by [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="8310f-160">**Nome do computador**</span><span class="sxs-lookup"><span data-stu-id="8310f-160">**Computer Name**</span></span>  
 <span data-ttu-id="8310f-161">O nome do computador do servidor que está executando o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8310f-161">The name of the server computer that is running [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="8310f-162">**Plataforma**</span><span class="sxs-lookup"><span data-stu-id="8310f-162">**Platform**</span></span>  
 <span data-ttu-id="8310f-163">O nome do sistema operacional, nome do fabricante e família de CPU do servidor.</span><span class="sxs-lookup"><span data-stu-id="8310f-163">The operating system name, manufacturer name, and CPU family of the server.</span></span>  
  
 <span data-ttu-id="8310f-164">**Sistema operacional**</span><span class="sxs-lookup"><span data-stu-id="8310f-164">**Operating System**</span></span>  
 <span data-ttu-id="8310f-165">A versão do [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows instalada no servidor.</span><span class="sxs-lookup"><span data-stu-id="8310f-165">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows version installed on the server.</span></span>  
  
 <span data-ttu-id="8310f-166">**Processadores**</span><span class="sxs-lookup"><span data-stu-id="8310f-166">**Processors**</span></span>  
 <span data-ttu-id="8310f-167">O número de processadores no servidor.</span><span class="sxs-lookup"><span data-stu-id="8310f-167">The number of processors on the server.</span></span>  
  
 <span data-ttu-id="8310f-168">**Memória do Sistema Operacional**</span><span class="sxs-lookup"><span data-stu-id="8310f-168">**Operating System Memory**</span></span>  
 <span data-ttu-id="8310f-169">O total de memória física no servidor, em megabytes.</span><span class="sxs-lookup"><span data-stu-id="8310f-169">The total amount of physical memory on the server, in megabytes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8310f-170">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8310f-170">See Also</span></span>  
 <span data-ttu-id="8310f-171">[Páginas de propriedades no SQL Server Management Studio](../ssms/property-pages-in-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="8310f-171">[Property Pages in SQL Server Management Studio](../ssms/property-pages-in-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="8310f-172">Conectar ao servidor &#40;página Logon&#41; Mecanismo de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="8310f-172">Connect to Server &#40;Login Page&#41; Database Engine</span></span>](../ssms/f1-help/connect-to-server-login-page-database-engine.md)  
  
  
