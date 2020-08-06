---
title: Sincronização da Web para Replicação de Mesclagem | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- merge replication synchronization [SQL Server replication]
- Internet [SQL Server replication], synchronization
- synchronization [SQL Server replication], Web Synchronization
- Web publishing [SQL Server replication], synchronization
- Web synchronization, about
- Web synchronization
ms.assetid: 84785aba-b2c1-4821-9e9d-a363c73dcb37
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ef7bf5a6f77d593a90508a0b69d02f8c0db04407
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582418"
---
# <a name="web-synchronization-for-merge-replication"></a><span data-ttu-id="bd26f-102">Sincronização da Web para replicação de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="bd26f-102">Web Synchronization for Merge Replication</span></span>
  <span data-ttu-id="bd26f-103">A sincronização da Web para replicação de mesclagem lhe permite replicar dados usando o protocolo HTTPS, e isso é útil nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="bd26f-103">Web synchronization for merge replication lets you replicate data by using the HTTPS protocol, and is useful for the following scenarios:</span></span>

-   <span data-ttu-id="bd26f-104">Sincronizando dados de usuários móveis pela Internet.</span><span class="sxs-lookup"><span data-stu-id="bd26f-104">Synchronizing data from mobile users over the Internet.</span></span>

-   <span data-ttu-id="bd26f-105">Sincronização de dados entre bancos de dados do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] por um firewall corporativo.</span><span class="sxs-lookup"><span data-stu-id="bd26f-105">Synchronizing data between [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases across a corporate firewall.</span></span>

 <span data-ttu-id="bd26f-106">Por exemplo, um representante de vendas ambulante pode usar a sincronização da Web.</span><span class="sxs-lookup"><span data-stu-id="bd26f-106">For example, a traveling sales representative can use Web synchronization.</span></span> <span data-ttu-id="bd26f-107">A empresa, [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)], tem representantes de vendas que viajam a várias lojas e fornecedores ao longo das suas regiões.</span><span class="sxs-lookup"><span data-stu-id="bd26f-107">The company, [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)], has sales representatives that travel to various stores and suppliers throughout their regions.</span></span> <span data-ttu-id="bd26f-108">Em viagens longas os representantes ficam em hotéis e precisam de uma forma conveniente para carregar os dados de vendas e baixar as atualizações de produtos no final de cada dia.</span><span class="sxs-lookup"><span data-stu-id="bd26f-108">On longer trips the representatives stay in hotels and need a convenient way to upload sales data and download any product updates at the end of each day.</span></span>

 <span data-ttu-id="bd26f-109">O departamento de TI de [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] configurou cada notebook com [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e habilitou a replicação de mesclagem para usar a sincronização da Web.</span><span class="sxs-lookup"><span data-stu-id="bd26f-109">The [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] IT department has configured each portable computer with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and has enabled merge replication to use Web synchronization.</span></span> <span data-ttu-id="bd26f-110">O Merge Agent em cada notebook possui uma URL de Internet que aponta para os componentes de replicação que são instalados em um computador que está executando [!INCLUDE[msCoName](../../includes/msconame-md.md)] Serviços de Informações da Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="bd26f-110">The Merge Agent on each portable computer has an Internet URL that points to the replication components that are installed on a computer that is running [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS).</span></span> <span data-ttu-id="bd26f-111">Esses componentes sincronizam o Assinante com o Publicador.</span><span class="sxs-lookup"><span data-stu-id="bd26f-111">These components synchronize the Subscriber with the Publisher.</span></span> <span data-ttu-id="bd26f-112">Agora, cada representante pode se conectar através de qualquer conexão de Internet disponível sem usar uma conexão discada remota, e pode carregar e baixar os dados apropriados.</span><span class="sxs-lookup"><span data-stu-id="bd26f-112">Each representative can now connect through any available Internet connection without using a remote dial-up connection, and can upload and download the appropriate data.</span></span> <span data-ttu-id="bd26f-113">A conexão de Internet usa o Protocolo SSL (Secure Sockets Layer); portanto, uma rede privada virtual (VPN) não é requerida.</span><span class="sxs-lookup"><span data-stu-id="bd26f-113">The Internet connection uses Secure Sockets Layer (SSL); therefore, a virtual private network (VPN) is not required.</span></span>

 <span data-ttu-id="bd26f-114">Para obter informações sobre como configurar os componentes que são necessários para a sincronização da Web, consulte [Configurar sincronização da Web](configure-web-synchronization.md), [configurar IIS para sincronização da Web](configure-iis-for-web-synchronization.md) e [configurar IIS 7 para sincronização da Web](configure-iis-7-for-web-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="bd26f-114">For information about how to configure the components that are required for Web synchronization, see [Configure Web Synchronization](configure-web-synchronization.md), [Configure IIS for Web Synchronization](configure-iis-for-web-synchronization.md), and [Configure IIS 7 for Web Synchronization](configure-iis-7-for-web-synchronization.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="bd26f-115">A sincronização da Web é projetada para sincronizar dados com computadores portáteis, dispositivos de mão e outros clientes.</span><span class="sxs-lookup"><span data-stu-id="bd26f-115">Web synchronization is designed for synchronizing data with portable computers, handheld devices, and other clients.</span></span> <span data-ttu-id="bd26f-116">A sincronização da Web não é destinada para aplicativos de alto volume de servidor a servidor.</span><span class="sxs-lookup"><span data-stu-id="bd26f-116">Web synchronization is not intended for high-volume server-to-server applications.</span></span>

## <a name="overview-of-how-web-synchronization-works"></a><span data-ttu-id="bd26f-117">Visão geral de como a sincronização da Web funciona</span><span class="sxs-lookup"><span data-stu-id="bd26f-117">Overview of How Web Synchronization Works</span></span>
 <span data-ttu-id="bd26f-118">Quando a sincronização da Web é usada, as atualizações no Assinante são empacotadas e enviadas como uma mensagem XML ao computador que está executando IIS usando o protocolo HTTPS.</span><span class="sxs-lookup"><span data-stu-id="bd26f-118">When Web synchronization is used, updates at the Subscriber are packaged and sent as an XML message to the computer that is running IIS by using the HTTPS protocol.</span></span> <span data-ttu-id="bd26f-119">O computador que está executando IIS então envia um comando ao Publicador em formato binário, normalmente usando TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="bd26f-119">The computer that is running IIS then sends the commands to the Publisher in a binary format, typically by using TCP/IP.</span></span> <span data-ttu-id="bd26f-120">Atualizações no Publicador são enviadas ao computador que está executando IIS e, então, são empacotadas como uma mensagem XML para entrega ao Assinante.</span><span class="sxs-lookup"><span data-stu-id="bd26f-120">Updates at the Publisher are sent to the computer that is running IIS and then packaged as an XML message for delivery to the Subscriber.</span></span>

 <span data-ttu-id="bd26f-121">A ilustração seguinte mostra alguns dos componentes que são envolvidos em sincronização da Web para replicação de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="bd26f-121">The following illustration shows some of the components that are involved in Web synchronization for merge replication.</span></span>

 <span data-ttu-id="bd26f-122">![Fluxo de dados e componentes de sincronização da Web](media/web-sync01.gif "Fluxo de dados e componentes de sincronização da Web")</span><span class="sxs-lookup"><span data-stu-id="bd26f-122">![Web synchronization components and data flow](media/web-sync01.gif "Web synchronization components and data flow")</span></span>

 <span data-ttu-id="bd26f-123">A sincronização da Web é uma opção apenas para assinatura pull; então, um Merge Agent sempre será executado no Assinante.</span><span class="sxs-lookup"><span data-stu-id="bd26f-123">Web synchronization is an option only for pull subscriptions; therefore, a Merge Agent will always run on the Subscriber.</span></span> <span data-ttu-id="bd26f-124">Esse Merge Agent pode ser o Merge Agent padrão, o MErge Agent do controle de Active X ou um aplicativo que fornece sincronização através do RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="bd26f-124">This Merge Agent can be the standard Merge Agent, the Merge Agent ActiveX control, or an application that provides synchronization through Replication Management Objects (RMO).</span></span> <span data-ttu-id="bd26f-125">Para especificar o local do computador que está executando o IIS, use o parâmetro **-InternetUrl** para o agente de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="bd26f-125">To specify the location of the computer that is running IIS, use the **-InternetUrl** parameter for the Merge Agent.</span></span>

 <span data-ttu-id="bd26f-126">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Replication Listener (Replisapi.dll) está configurado no computador que está executando IIS e é responsável pelo manuseio das mensagens enviadas para o servidor do Publicador e dos Assinantes.</span><span class="sxs-lookup"><span data-stu-id="bd26f-126">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Replication Listener (Replisapi.dll) is configured on the computer that is running IIS and is responsible for handling messages that are sent to the server from the Publisher and Subscribers.</span></span> <span data-ttu-id="bd26f-127">Cada nó na topologia controla o fluxo de dados XML usando o Reconciliador de Replicação de Mesclagem (Replrec.dll).</span><span class="sxs-lookup"><span data-stu-id="bd26f-127">Each node in the topology handles the XML data stream by using the Merge Replication Reconciler (Replrec.dll).</span></span>

 <span data-ttu-id="bd26f-128">O[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] ou uma versão posterior é requerida para todos os computadores que participam de sincronização da Web.</span><span class="sxs-lookup"><span data-stu-id="bd26f-128">[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or a later version is required for all computers that participate in Web synchronization.</span></span>

### <a name="synchronization-process"></a><span data-ttu-id="bd26f-129">Processo de Sincronização</span><span class="sxs-lookup"><span data-stu-id="bd26f-129">Synchronization Process</span></span>
 <span data-ttu-id="bd26f-130">As etapas seguintes acontecem durante a sincronização:</span><span class="sxs-lookup"><span data-stu-id="bd26f-130">The following steps occur during synchronization:</span></span>

1.  <span data-ttu-id="bd26f-131">O Merge Agent é iniciado no Assinante.</span><span class="sxs-lookup"><span data-stu-id="bd26f-131">The Merge Agent is started at the Subscriber.</span></span> <span data-ttu-id="bd26f-132">O agente faz o seguinte:</span><span class="sxs-lookup"><span data-stu-id="bd26f-132">The agent does the following:</span></span>

    1.  <span data-ttu-id="bd26f-133">Faz uma conexão SQL ao banco de dados de assinatura.</span><span class="sxs-lookup"><span data-stu-id="bd26f-133">Makes an SQL connection to the subscription database.</span></span>

    2.  <span data-ttu-id="bd26f-134">Extrai quaisquer alterações do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="bd26f-134">Extracts any changes from the database.</span></span>

    3.  <span data-ttu-id="bd26f-135">Faz uma solicitação HTTPS ao computador que está executando IIS.</span><span class="sxs-lookup"><span data-stu-id="bd26f-135">Makes an HTTPS request to the computer that is running IIS.</span></span>

    4.  <span data-ttu-id="bd26f-136">Carrega as alterações de dados como uma mensagem de XML.</span><span class="sxs-lookup"><span data-stu-id="bd26f-136">Uploads data changes as an XML message.</span></span>

2.  <span data-ttu-id="bd26f-137">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Replication Listener e Reconciliador de Replicação de Mesclagem que estão hospedados no computador que está executando IIS, fazem o seguinte.</span><span class="sxs-lookup"><span data-stu-id="bd26f-137">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Replication Listener and Merge Replication Reconciler that are hosted on the computer that is running IIS do the following:</span></span>

    1.  <span data-ttu-id="bd26f-138">Respondem à solicitação de HTTPS.</span><span class="sxs-lookup"><span data-stu-id="bd26f-138">Respond to the HTTPS request.</span></span>

    2.  <span data-ttu-id="bd26f-139">Fazem uma conexão SQL ao banco de dados de publicação.</span><span class="sxs-lookup"><span data-stu-id="bd26f-139">Make an SQL connection to the publication database.</span></span>

    3.  <span data-ttu-id="bd26f-140">Aplicam as alterações carregadas ao banco de dados de publicação.</span><span class="sxs-lookup"><span data-stu-id="bd26f-140">Apply the upload changes to the publication database.</span></span>

    4.  <span data-ttu-id="bd26f-141">Extraem as alterações de download para o Assinante.</span><span class="sxs-lookup"><span data-stu-id="bd26f-141">Extract the download changes for the Subscriber.</span></span>

    5.  <span data-ttu-id="bd26f-142">Enviam de volta uma resposta de HTTPS ao Merge Agent.</span><span class="sxs-lookup"><span data-stu-id="bd26f-142">Send an HTTPS response back to the Merge Agent.</span></span>

3.  <span data-ttu-id="bd26f-143">O Merge Agent no Assinante oferece suporte à resposta HTTPS e aplica as alterações de download ao banco de dados da assinatura.</span><span class="sxs-lookup"><span data-stu-id="bd26f-143">The Merge Agent at the Subscriber then accepts the HTTPS response and applies the download changes to the subscription database.</span></span>

## <a name="see-also"></a><span data-ttu-id="bd26f-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bd26f-144">See Also</span></span>
 <span data-ttu-id="bd26f-145">[Configurar](configure-web-synchronization.md) [topologias de sincronização da Web para sincronização da Web](topologies-for-web-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="bd26f-145">[Configure Web Synchronization](configure-web-synchronization.md) [Topologies for Web Synchronization](topologies-for-web-synchronization.md)</span></span>


