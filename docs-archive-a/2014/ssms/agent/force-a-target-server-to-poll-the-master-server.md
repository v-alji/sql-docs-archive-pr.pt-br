---
title: Forçar um servidor de destino a sondar o servidor mestre | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- forcing master server polling
- polling master servers [SQL Server]
- master servers [SQL Server], polling
- target servers [SQL Server], polling the master server
ms.assetid: f1189a47-5ac3-45e2-9c5f-847810672279
author: stevestein
ms.author: sstein
ms.openlocfilehash: b37bf19bfe8e8fb55c29c8d94c28a341d06df5da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569020"
---
# <a name="force-a-target-server-to-poll-the-master-server"></a><span data-ttu-id="08890-102">Force a Target Server to Poll the Master Server</span><span class="sxs-lookup"><span data-stu-id="08890-102">Force a Target Server to Poll the Master Server</span></span>
  <span data-ttu-id="08890-103">Este tópico descreve como obrigar um servidor de destino a sondar o servidor mestre.</span><span class="sxs-lookup"><span data-stu-id="08890-103">This topic describes how to force a target server to poll the master server.</span></span> <span data-ttu-id="08890-104">O servidor de destino deve estar registrado no servidor mestre.</span><span class="sxs-lookup"><span data-stu-id="08890-104">The target server must be a registered server on the master server.</span></span>  
  
 <span data-ttu-id="08890-105">Um trabalho é uma série especificada de ações que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent executa.</span><span class="sxs-lookup"><span data-stu-id="08890-105">A job is a specified series of actions that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent performs.</span></span> <span data-ttu-id="08890-106">Um trabalho multisservidor é um trabalho executado por um servidor mestre em um ou mais servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="08890-106">A multiserver job is a job that a master server runs on one or more target servers.</span></span> <span data-ttu-id="08890-107">Cada servidor de destino pode executar uma instância do mesmo trabalho ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="08890-107">Each target server can run one instance of the same job at the same time.</span></span> <span data-ttu-id="08890-108">Cada servidor de destino sonda o servidor mestre periodicamente, baixa uma cópia dos eventuais trabalhos novos a ele atribuídos e, em seguida, desconecta-se.</span><span class="sxs-lookup"><span data-stu-id="08890-108">Each target server periodically polls the master server, downloads a copy of any new jobs assigned to the target server, and then disconnects.</span></span> <span data-ttu-id="08890-109">O servidor de destino executa o trabalho localmente e, depois, reconecta-se ao servidor mestre para carregar o status do resultado do trabalho.</span><span class="sxs-lookup"><span data-stu-id="08890-109">The target server runs the job locally and then reconnects to the master server to upload the job outcome status.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="08890-110">Se o servidor mestre não estiver acessível quando o servidor de destino tentar carregar o status do trabalho, este será colocado em spool até que o servidor mestre esteja novamente acessível.</span><span class="sxs-lookup"><span data-stu-id="08890-110">If the master server is inaccessible when the target server tries to upload job status, the job status is spooled until the master server can be accessed.</span></span>  
  
-   <span data-ttu-id="08890-111">**Antes de começar:**  [Limitações e Restrições](#Restrictions), [Segurança](#Security)</span><span class="sxs-lookup"><span data-stu-id="08890-111">**Before you begin:**  [Limitations and Restrictions](#Restrictions), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="08890-112">**Para forçar um servidor de destino a sondar o servidor mestre usando:**  [SQL Server Management Studio](#SSMS)</span><span class="sxs-lookup"><span data-stu-id="08890-112">**To force a target server to poll the master server, using:**  [SQL Server Management Studio](#SSMS)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="08890-113">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="08890-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="08890-114">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="08890-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="08890-115">O servidor de destino deve estar registrado no servidor mestre.</span><span class="sxs-lookup"><span data-stu-id="08890-115">The target server must be a registered server on the master server.</span></span> <span data-ttu-id="08890-116">Você deve executar as instruções fornecidas neste tópico do servidor mestre.</span><span class="sxs-lookup"><span data-stu-id="08890-116">You must run the instructions given in this topic from the master server.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="08890-117">Segurança</span><span class="sxs-lookup"><span data-stu-id="08890-117">Security</span></span>  
 <span data-ttu-id="08890-118">Para obter informações detalhadas, consulte [Implement SQL Server Agent Security](implement-sql-server-agent-security.md) e [Choose the Right SQL Server Agent Service Account for Multiserver Environments](choose-the-right-sql-server-agent-service-account-for-multiserver-environments.md).</span><span class="sxs-lookup"><span data-stu-id="08890-118">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md) and [Choose the Right SQL Server Agent Service Account for Multiserver Environments](choose-the-right-sql-server-agent-service-account-for-multiserver-environments.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="08890-119">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="08890-119">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="08890-120">**Para forçar um servidor de destino a sondar o servidor mestre**</span><span class="sxs-lookup"><span data-stu-id="08890-120">**To force a target server to poll the master server**</span></span>  
  
1.  <span data-ttu-id="08890-121">No **Pesquisador de Objetos**, expanda o servidor mestre.</span><span class="sxs-lookup"><span data-stu-id="08890-121">In **Object Explorer**, expand the master server.</span></span>  
  
2.  <span data-ttu-id="08890-122">Clique com o botão direito do mouse em **SQL Server Agent**, aponte para **Administração Multisservidor**e clique em **Gerenciar Servidores de Destino**.</span><span class="sxs-lookup"><span data-stu-id="08890-122">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Manage Target Servers**.</span></span>  
  
3.  <span data-ttu-id="08890-123">Clique em um servidor de destino e, em seguida, em **Forçar Sondagem**.</span><span class="sxs-lookup"><span data-stu-id="08890-123">Click a target server, and then click **Force Poll**.</span></span>  
  
  
