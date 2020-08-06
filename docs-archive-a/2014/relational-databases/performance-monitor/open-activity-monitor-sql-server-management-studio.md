---
title: Abrir o Monitor de Atividade (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Activity Monitor [SQL Server], setting the refresh interval
- refresh interval for Activity Monitor
- Activity Monitor [SQL Server], opening
- opening Activity Monitor
ms.assetid: 0a6eeb16-f02b-479d-9a60-543e40ebf46b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ea74122ad18a0a1ede5eef1e09684606ca0ce073
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684665"
---
# <a name="open-activity-monitor-sql-server-management-studio"></a><span data-ttu-id="b8b30-102">Abrir o Monitor de Atividade (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="b8b30-102">Open Activity Monitor (SQL Server Management Studio)</span></span>
  <span data-ttu-id="b8b30-103">Este tópico descreve como abrir o Monitor de Atividade para obter informações sobre os processos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e como esses processos afetam a instância atual do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8b30-103">This topic describes how to open the Activity Monitor to obtain information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processes and how these processes affect the current instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b8b30-104">Descreve também como definir o intervalo de atualização do Monitor de Atividade.</span><span class="sxs-lookup"><span data-stu-id="b8b30-104">It also describes how to set the refresh interval of the Activity Monitor.</span></span>  
  
 <span data-ttu-id="b8b30-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="b8b30-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b8b30-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="b8b30-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b8b30-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="b8b30-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b8b30-108">**Para abrir o Monitor de Atividade usando:**</span><span class="sxs-lookup"><span data-stu-id="b8b30-108">**To open the Activity Monitor using:**</span></span>  
  
     [<span data-ttu-id="b8b30-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b8b30-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   <span data-ttu-id="b8b30-110">**Para definir o intervalo de atualização usando:**  [SQL Server Management Studio](#Refresh)</span><span class="sxs-lookup"><span data-stu-id="b8b30-110">**To set the refresh interval using:**  [SQL Server Management Studio](#Refresh)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b8b30-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="b8b30-111">Before You Begin</span></span>  
 <span data-ttu-id="b8b30-112">O Monitor de Atividade executa consultas na instância monitorada a fim de obter informações para os painéis de exibição do Monitor de Atividade.</span><span class="sxs-lookup"><span data-stu-id="b8b30-112">Activity Monitor runs queries on the monitored instance to obtain information for the Activity Monitor display panes.</span></span> <span data-ttu-id="b8b30-113">Quando o intervalo de atualização for definido para menos de 10 segundos, o tempo usado para executar essas consultas poderá afetar o desempenho do servidor.</span><span class="sxs-lookup"><span data-stu-id="b8b30-113">When the refresh interval is set to less than 10 seconds, the time that is used to run these queries can affect server performance</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b8b30-114">Segurança</span><span class="sxs-lookup"><span data-stu-id="b8b30-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b8b30-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="b8b30-115">Permissions</span></span>  
 <span data-ttu-id="b8b30-116">Para exibir o Monitor de Atividade, um usuário deve ter a permissão VIEW SERVER STATE.</span><span class="sxs-lookup"><span data-stu-id="b8b30-116">To view the Activity Monitor, a user must have VIEW SERVER STATE permission.</span></span> <span data-ttu-id="b8b30-117">Para exibir a seção E/S de Arquivo de Dados do Monitor de Atividade, você deve ter a permissão CREATE DATABASE, ALTER ANY DATABASE ou VIEW ANY DEFINITION além da permissão VIEW SERVER STATE.</span><span class="sxs-lookup"><span data-stu-id="b8b30-117">To view the Data File I/O section of Activity Monitor, you must have CREATE DATABASE, ALTER ANY DATABASE, or VIEW ANY DEFINITION permission in addition to VIEW SERVER STATE.</span></span>  
  
 <span data-ttu-id="b8b30-118">Para executar KILL em um processo, o usuário deve ser um membro das funções de servidor fixas sysadmin ou processadmin.</span><span class="sxs-lookup"><span data-stu-id="b8b30-118">To KILL a process, a user must be a member of the sysadmin or processadmin fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b8b30-119">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b8b30-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-open-activity-monitor-in-sql-server-management-studio"></a><span data-ttu-id="b8b30-120">Para abrir o Monitor de Atividade no SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b8b30-120">To open Activity Monitor in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="b8b30-121">Na barra de ferramentas padrão do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , clique em **Monitor de Atividade**.</span><span class="sxs-lookup"><span data-stu-id="b8b30-121">On the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] standard toolbar, click **Activity Monitor**.</span></span>  
  
2.  <span data-ttu-id="b8b30-122">Na caixa de diálogo **Conectar ao Servidor** , selecione o nome do servidor e o modo de autenticação e clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="b8b30-122">In the **Connect to Server** dialog box, select the server name and authentication mode, and then click **Connect**.</span></span>  
  
 <span data-ttu-id="b8b30-123">Também é possível abrir o Monitor de Atividade a qualquer momento pressionando CTRL+ALT A.</span><span class="sxs-lookup"><span data-stu-id="b8b30-123">You can also open Activity Monitor at any time by pressing CTRL+ALT A.</span></span>  
  
#### <a name="to-open-activity-monitor-in-object-explorer"></a><span data-ttu-id="b8b30-124">Para abrir o Monitor de Atividade no Pesquisador de Objetos</span><span class="sxs-lookup"><span data-stu-id="b8b30-124">To open Activity Monitor in Object Explorer</span></span>  
  
-   <span data-ttu-id="b8b30-125">No Pesquisador de objetos, clique com o botão direito do mouse no nome da instância e selecione **Monitor de atividade**.</span><span class="sxs-lookup"><span data-stu-id="b8b30-125">In Object Explorer, right-click the instance name, and then select **Activity Monitor**.</span></span>  
  
#### <a name="to-open-activity-monitor-when-opening-sql-server-management-studio"></a><span data-ttu-id="b8b30-126">Para abrir o Monitor de Atividade ao abrir o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b8b30-126">To open Activity Monitor when opening SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="b8b30-127">No menu **Ferramentas** , clique em **Opções**.</span><span class="sxs-lookup"><span data-stu-id="b8b30-127">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="b8b30-128">Na caixa de diálogo **Opções** , expanda **Ambiente**e, em seguida, selecione **Geral**.</span><span class="sxs-lookup"><span data-stu-id="b8b30-128">In the **Options** dialog box, expand **Environment**, and then select **General**.</span></span>  
  
3.  <span data-ttu-id="b8b30-129">Na caixa **Na inicialização** , selecione **Abrir Pesquisador de Objetos e Monitor de Atividade**.</span><span class="sxs-lookup"><span data-stu-id="b8b30-129">In the **At startup** box, select **Open Object Explorer and Activity Monitor**.</span></span>  
  
4.  <span data-ttu-id="b8b30-130">Para ativar as alterações, feche e reabra o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8b30-130">To activate the changes, close and reopen [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
###  <a name="to-set-the-activity-monitor-refresh-interval"></a><a name="Refresh"></a><span data-ttu-id="b8b30-131">Para definir o intervalo de atualização do monitor de atividade</span><span class="sxs-lookup"><span data-stu-id="b8b30-131">To Set the Activity Monitor Refresh Interval</span></span>  
  
-   <span data-ttu-id="b8b30-132">Abra o Monitor de Atividade.</span><span class="sxs-lookup"><span data-stu-id="b8b30-132">Open the Activity Monitor.</span></span>  
  
-   <span data-ttu-id="b8b30-133">Clique com o botão direito do mouse em **Visão Geral**, selecione **Intervalo de Atualização**e selecione o intervalo em que o Monitor de Atividade deve obter novas informações sobre a instância.</span><span class="sxs-lookup"><span data-stu-id="b8b30-133">Right-click **Overview**, select **Refresh Interval**, and then select the interval in which Activity Monitor should obtain new instance information.</span></span>  
  
  
