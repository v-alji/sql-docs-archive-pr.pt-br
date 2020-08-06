---
title: Distribuidor | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.replicationutilities.selectdistributor.f1
ms.assetid: 787f0e9c-09dd-438a-bc04-5b8f99c127b8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c601a540088b5cd9d7a2033510a5cf9b83c3170e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569914"
---
# <a name="distributor"></a><span data-ttu-id="582ad-102">Distribuidor</span><span class="sxs-lookup"><span data-stu-id="582ad-102">Distributor</span></span>
  <span data-ttu-id="582ad-103">A página **Distribuidor** é exibida no Assistente para Configurar a Distribuição e no Assistente para Nova Publicação.</span><span class="sxs-lookup"><span data-stu-id="582ad-103">The **Distributor** page appears in the Configure Distribution Wizard and in the New Publication Wizard.</span></span> <span data-ttu-id="582ad-104">O Distribuidor é um servidor que contém o banco de dados de distribuição e armazena metadados e dados de histórico para todos os tipos de replicação.</span><span class="sxs-lookup"><span data-stu-id="582ad-104">The Distributor is a server that contains the distribution database and stores metadata and history data for all types of replication.</span></span> <span data-ttu-id="582ad-105">O Distribuidor também armazena transações para replicação transacional.</span><span class="sxs-lookup"><span data-stu-id="582ad-105">The Distributor also stores transactions for transactional replication.</span></span> <span data-ttu-id="582ad-106">O Distribuidor pode ser o mesmo servidor que o Publicador (um Distribuidor local) ou pode ser um servidor separado do Publicador (um Distribuidor remoto).</span><span class="sxs-lookup"><span data-stu-id="582ad-106">The Distributor can be the same server as the Publisher (a local Distributor) or it can be a separate server from the Publisher (a remote Distributor).</span></span> <span data-ttu-id="582ad-107">A função do Distribuidor varia, dependendo do tipo de replicação implementado.</span><span class="sxs-lookup"><span data-stu-id="582ad-107">The role of the Distributor varies, depending on which type of replication you implement.</span></span> <span data-ttu-id="582ad-108">Em geral, sua função é muito maior para replicação transacional do que para replicação de mesclagem e replicação de instantâneo.</span><span class="sxs-lookup"><span data-stu-id="582ad-108">In general, its role is much greater for transactional replication than it is for merge replication and snapshot replication.</span></span> <span data-ttu-id="582ad-109">A replicação de mesclagem e de instantâneo usam normalmente um Distribuidor local, mas a replicação transacional em um sistema muito ocupado pode se beneficiar de usar um Distribuidor remoto.</span><span class="sxs-lookup"><span data-stu-id="582ad-109">Merge and snapshot replication typically use a local Distributor, but transactional replication on a very busy system can benefit from using a remote Distributor.</span></span>  
  
 <span data-ttu-id="582ad-110">O Distribuidor usa esses recursos adicionais no servidor onde fica localizado:</span><span class="sxs-lookup"><span data-stu-id="582ad-110">The Distributor uses these additional resources on the server where it is located:</span></span>  
  
-   <span data-ttu-id="582ad-111">Espaço em disco adicional, se os arquivos de instantâneo para a publicação forem armazenados nele (que é o que geralmente acontece).</span><span class="sxs-lookup"><span data-stu-id="582ad-111">Additional disk space if the snapshot files for the publication are stored on it (which they typically are).</span></span>  
  
-   <span data-ttu-id="582ad-112">Espaço em disco adicional para armazenar o banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="582ad-112">Additional disk space to store the distribution database.</span></span>  
  
-   <span data-ttu-id="582ad-113">Uso de processador adicional por agentes de replicação para assinaturas push executadas no Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="582ad-113">Additional processor usage by replication agents for push subscriptions running on the Distributor.</span></span>  
  
 <span data-ttu-id="582ad-114">O servidor selecionado como Distribuidor deve ter espaço em disco adequado e potência no processador para dar suporte a replicação e a qualquer outra atividade naquele servidor.</span><span class="sxs-lookup"><span data-stu-id="582ad-114">The server you select as the Distributor should have adequate disk space and processor power to support replication and any other activities on that server.</span></span>  
  
## <a name="options"></a><span data-ttu-id="582ad-115">Opções</span><span class="sxs-lookup"><span data-stu-id="582ad-115">Options</span></span>  
 <span data-ttu-id="582ad-116">**'\<ServerName>' atuará como um Distribuidor próprio; o SQL Server criará um banco de dados e um log de distribuição**</span><span class="sxs-lookup"><span data-stu-id="582ad-116">**'\<ServerName>' will act as its own Distributor; SQL Server will create a distribution database and log**</span></span>  
 <span data-ttu-id="582ad-117">Selecione essa opção para configurar o servidor ao qual você está conectado como um Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="582ad-117">Select this option to configure the server you are connected to as a Distributor.</span></span>  
  
 <span data-ttu-id="582ad-118">**Usar este servidor como o Distribuidor (Observação: o servidor selecionado já deve estar configurado como Distribuidor)**</span><span class="sxs-lookup"><span data-stu-id="582ad-118">**Use the following server as the Distributor (Note: the server you select must already be configured as a Distributor)**</span></span>  
 <span data-ttu-id="582ad-119">Selecione essa opção e clique no nome de um servidor abaixo para configurar outro servidor como o Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="582ad-119">Select this option and then click on the name of a server below to configure another server as the Distributor.</span></span>  
  
 <span data-ttu-id="582ad-120">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="582ad-120">**Add**</span></span>  
 <span data-ttu-id="582ad-121">Se o servidor que você quer usar como Distribuidor não estiver na lista, clique em **Adicionar** para identificar o servidor e adicioná-lo à lista.</span><span class="sxs-lookup"><span data-stu-id="582ad-121">If the server you want to use as a Distributor is not listed, click **Add** to identify the server and add it to the list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="582ad-122">Para usar um servidor remoto como Distribuidor, o servidor remoto já deverá estar configurado como um Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="582ad-122">To use a remote server as the Distributor, the remote server must already be configured as a Distributor.</span></span> <span data-ttu-id="582ad-123">O servidor em que esse assistente está sendo executado deve ser habilitado como um Publicador naquele Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="582ad-123">The server against which this wizard is running must be enabled as a Publisher on that Distributor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="582ad-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="582ad-124">See Also</span></span>  
 <span data-ttu-id="582ad-125">[Configurar Distribuição](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="582ad-125">[Configure Distribution](configure-distribution.md) </span></span>  
 [<span data-ttu-id="582ad-126">Configurar a publicação e a distribuição</span><span class="sxs-lookup"><span data-stu-id="582ad-126">Configure Publishing and Distribution</span></span>](configure-publishing-and-distribution.md)  
  
  
