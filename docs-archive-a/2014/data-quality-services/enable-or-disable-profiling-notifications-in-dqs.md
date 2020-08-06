---
title: Habilitar ou desabilitar notificações de criação de perfil no DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
helpviewer_keywords:
- enable notifications
- notifications,enable
- notifications,disable
ms.assetid: e439bb29-60cc-4afd-a79a-f629b8d843c1
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: b3b5e8cec1cac3eb1ce4357480c0f994a33d4c40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680641"
---
# <a name="enable-or-disable-profiling-notifications-in-dqs"></a><span data-ttu-id="72287-102">Habilitar ou desabilitar notificações de criação de perfil no DQS</span><span class="sxs-lookup"><span data-stu-id="72287-102">Enable or Disable Profiling Notifications in DQS</span></span>
  <span data-ttu-id="72287-103">Este tópico descreve como habilitar ou desabilitar notificações de criação de perfil no [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="72287-103">This topic describes how to enable or disable profiling notifications in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="72287-104">Por padrão, as notificações de criação de perfil estão habilitadas no DQS.</span><span class="sxs-lookup"><span data-stu-id="72287-104">By default, profiling notifications are enabled in DQS.</span></span> <span data-ttu-id="72287-105">As notificações de criação de perfil informam fatos importantes sobre a fonte de dados e a efetividade da atividade atual executada nos dados.</span><span class="sxs-lookup"><span data-stu-id="72287-105">Profiling notifications tell you important facts about the data source and the effectiveness of the current activity performed on the data.</span></span> <span data-ttu-id="72287-106">Para obter mais informações, consulte [Data Profiling and Notifications in DQS](../../2014/data-quality-services/data-profiling-and-notifications-in-dqs.md).</span><span class="sxs-lookup"><span data-stu-id="72287-106">For more information, see [Data Profiling and Notifications in DQS](../../2014/data-quality-services/data-profiling-and-notifications-in-dqs.md).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="72287-107">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="72287-107">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="72287-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="72287-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="72287-109">Permissões</span><span class="sxs-lookup"><span data-stu-id="72287-109">Permissions</span></span>  
 <span data-ttu-id="72287-110">Você deve ter a função dqs_administrator no banco de dados DQS_MAIN para habilitar as notificações.</span><span class="sxs-lookup"><span data-stu-id="72287-110">You must have the dqs_administrator role on the DQS_MAIN database to enable notifications.</span></span>  
  
##  <a name="enable-or-disable-profiling-notifications"></a><a name="Enable"></a> <span data-ttu-id="72287-111">Habilitar ou desabilitar notificações de criação de perfil</span><span class="sxs-lookup"><span data-stu-id="72287-111">Enable or Disable Profiling Notifications</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="72287-112">[Execute o aplicativo Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="72287-112">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="72287-113">Na tela inicial do [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , clique em **Configuração**.</span><span class="sxs-lookup"><span data-stu-id="72287-113">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Configuration**.</span></span>  
  
3.  <span data-ttu-id="72287-114">Em seguida, clique na guia **Configurações Gerais** .</span><span class="sxs-lookup"><span data-stu-id="72287-114">Next, click the **General Settings** tab.</span></span>  
  
4.  <span data-ttu-id="72287-115">Marque ou desmarque a caixa de seleção **Habilitar Notificações** para desabilitar ou habilitar as notificações de criação de perfil para várias atividades no DQS.</span><span class="sxs-lookup"><span data-stu-id="72287-115">Clear or select the **Enable Notifications** check box to disable or enable profiling notifications for various activities in DQS.</span></span>  
  
5.  <span data-ttu-id="72287-116">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="72287-116">Click **Close**.</span></span>  
  
  
