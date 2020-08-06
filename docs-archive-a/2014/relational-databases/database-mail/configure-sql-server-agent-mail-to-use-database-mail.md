---
title: Configurar o SQL Server Agent Mail para usar o Database Mail | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Database Mail [SQL Server], SQL Server Agent Mail
- SQL Server Agent Mail
ms.assetid: 4b8b61bd-4bd1-43cd-b6e5-c6ed2e101dce
author: stevestein
ms.author: sstein
ms.openlocfilehash: 31d116c0bc8d7e148fc2ef6d2e344400516ad923
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678789"
---
# <a name="configure-sql-server-agent-mail-to-use-database-mail"></a><span data-ttu-id="b2afb-102">Configurar o SQL Server Agent Mail para usar o Database Mail</span><span class="sxs-lookup"><span data-stu-id="b2afb-102">Configure SQL Server Agent Mail to Use Database Mail</span></span>
  <span data-ttu-id="b2afb-103">Este tópico descreve como configurar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent para usar o Database Mail para enviar notificação e alertas no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2afb-103">This topic describes how to configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to use Database Mail to send notification and alerts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="b2afb-104">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="b2afb-104">**Before you begin:**</span></span>  
  
-   [<span data-ttu-id="b2afb-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="b2afb-105">Prerequisites</span></span>](#Prerequisites)  
  
-   [<span data-ttu-id="b2afb-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="b2afb-106">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="b2afb-107">Para configurar o SQL Server Agent para usar o Database Mail, usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b2afb-107">To Configure SQL Server Agent to use Database Mail, using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="b2afb-108">Tarefas de acompanhamento</span><span class="sxs-lookup"><span data-stu-id="b2afb-108">Follow-up Tasks</span></span>](#Follow_Up)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b2afb-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="b2afb-109">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="b2afb-110">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="b2afb-110">Prerequisites</span></span>  
  
-   <span data-ttu-id="b2afb-111">Habilite o Database Mail.</span><span class="sxs-lookup"><span data-stu-id="b2afb-111">Enable Database Mail.</span></span>  
  
-   <span data-ttu-id="b2afb-112">Crie uma conta do Database Mail para a conta de serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent a ser usada.</span><span class="sxs-lookup"><span data-stu-id="b2afb-112">Create a Database Mail account for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account to use.</span></span>  
  
-   <span data-ttu-id="b2afb-113">Crie um perfil do Database Mail para a conta de serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent a usar e adicione o usuário a **DatabaseMailUserRole** no banco de dados **msdb** .</span><span class="sxs-lookup"><span data-stu-id="b2afb-113">Create a Database Mail profile for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account to use and add the user to the **DatabaseMailUserRole** in the **msdb** database.</span></span>  
  
-   <span data-ttu-id="b2afb-114">Defina o perfil como o perfil padrão para o banco de dados **msdb** .</span><span class="sxs-lookup"><span data-stu-id="b2afb-114">Set the profile as the default profile for the **msdb** database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b2afb-115">Segurança</span><span class="sxs-lookup"><span data-stu-id="b2afb-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b2afb-116">Permissões</span><span class="sxs-lookup"><span data-stu-id="b2afb-116">Permissions</span></span>  
 <span data-ttu-id="b2afb-117">O usuário que cria as contas de perfis e executa procedimentos armazenados deve ser membro da função de servidor fixa sysadmin.</span><span class="sxs-lookup"><span data-stu-id="b2afb-117">The user creating the profiles accounts and executing stored procedures should be a member of the sysadmin fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b2afb-118">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b2afb-118">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="b2afb-119">**Para configurar o SQL Server Agent para usar o Database Mail**</span><span class="sxs-lookup"><span data-stu-id="b2afb-119">**To configure SQL Server Agent to use Database Mail**</span></span>  
  
-   <span data-ttu-id="b2afb-120">No Pesquisador de Objetos, expanda uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b2afb-120">In Object Explorer, expand a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
-   <span data-ttu-id="b2afb-121">Clique com o botão direito do mouse em **SQL Server Agent**e então clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="b2afb-121">Right-click **SQL Server Agent**, and then click **Properties**.</span></span>  
  
-   <span data-ttu-id="b2afb-122">Clique em **Sistema de Alerta**.</span><span class="sxs-lookup"><span data-stu-id="b2afb-122">Click **Alert System**.</span></span>  
  
-   <span data-ttu-id="b2afb-123">Selecione **Habilitar Perfil de Email**.</span><span class="sxs-lookup"><span data-stu-id="b2afb-123">Select **Enable Mail Profile**.</span></span>  
  
-   <span data-ttu-id="b2afb-124">Na lista **Sistema de email** , selecione **Database Mail**.</span><span class="sxs-lookup"><span data-stu-id="b2afb-124">In the **Mail system** list, select **Database Mail**.</span></span>  
  
-   <span data-ttu-id="b2afb-125">Na lista **Perfil de email**, selecione um perfil de email para o Database Mail.</span><span class="sxs-lookup"><span data-stu-id="b2afb-125">In the **Mail profile list**, select a mail profile for Database Mail.</span></span>  
  
-   <span data-ttu-id="b2afb-126">Reinicie o SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="b2afb-126">Restart SQL Server Agent.</span></span>  
  
##  <a name="follow-up-tasks"></a><a name="Follow_Up"></a> <span data-ttu-id="b2afb-127">Tarefas de acompanhamento</span><span class="sxs-lookup"><span data-stu-id="b2afb-127">Follow-up Tasks</span></span>  
 <span data-ttu-id="b2afb-128">As tarefas a seguir são necessárias para concluir a configuração do Agent a fim de enviar alertas e notificações.</span><span class="sxs-lookup"><span data-stu-id="b2afb-128">The following tasks are necessary to complete the configuration of Agent to send alerts and notifications.</span></span>  
  
-   [<span data-ttu-id="b2afb-129">Alertas</span><span class="sxs-lookup"><span data-stu-id="b2afb-129">Alerts</span></span>](../../ssms/agent/alerts.md)  
  
     <span data-ttu-id="b2afb-130">Os alertas podem ser configurados para notificar um operador sobre um evento de banco de dados em particular ou uma condição do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="b2afb-130">Alerts can be configured to notify an operator of a particular database event or operating system condition.</span></span>  
  
-   [<span data-ttu-id="b2afb-131">Operadores</span><span class="sxs-lookup"><span data-stu-id="b2afb-131">Operators</span></span>](../../ssms/agent/operators.md)  
  
     <span data-ttu-id="b2afb-132">Os operadores são alias de pessoas ou grupos que podem receber notificação eletrônica.</span><span class="sxs-lookup"><span data-stu-id="b2afb-132">Operators are aliases for people or groups that can receive electronic notification</span></span>  
  
  
