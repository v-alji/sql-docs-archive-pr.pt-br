---
title: Formatar endereços de pager para alertas | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- pager addresses [SQL Server]
- SQL Server Agent, alerts
- formats [SQL Server], pager addresses
- pager notifications [SQL Server]
- addresses [SQL Server]
- alerts [SQL Server], pager addresses
ms.assetid: a9797d01-1050-442c-9038-ed4bfee1e76a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 471f9a4958f51491b312d89239a2204c907e25e5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569016"
---
# <a name="format-pager-addresses-for-alerts"></a><span data-ttu-id="7d574-102">Format Pager Addresses for Alerts</span><span class="sxs-lookup"><span data-stu-id="7d574-102">Format Pager Addresses for Alerts</span></span>
  <span data-ttu-id="7d574-103">Este tópico descreve como formatar endereços de pager para [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alertas de agente no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o ou o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7d574-103">This topic describes how to format pager addresses for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="7d574-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="7d574-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7d574-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="7d574-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7d574-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="7d574-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7d574-107">**Para formatar endereços de pager, usando:**</span><span class="sxs-lookup"><span data-stu-id="7d574-107">**To format pager addresses, using:**</span></span>  
  
     [<span data-ttu-id="7d574-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7d574-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7d574-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="7d574-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7d574-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="7d574-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7d574-111">Permissões</span><span class="sxs-lookup"><span data-stu-id="7d574-111">Permissions</span></span>  
 <span data-ttu-id="7d574-112">Por padrão, os membros da função de servidor fixa **sysadmin** podem exibir as informações sobre um alerta.</span><span class="sxs-lookup"><span data-stu-id="7d574-112">By default, members of the **sysadmin** fixed server role can view information about an alert.</span></span> <span data-ttu-id="7d574-113">Deve ser concedida a outros usuários a função de banco de dados fixa **SQLAgentOperatorRole** no banco de dados **msdb** .</span><span class="sxs-lookup"><span data-stu-id="7d574-113">Other users must be granted the **SQLAgentOperatorRole** fixed database role in the **msdb** database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7d574-114">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7d574-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-format-pager-addresses"></a><span data-ttu-id="7d574-115">Para formatar endereços de pager</span><span class="sxs-lookup"><span data-stu-id="7d574-115">To format pager addresses</span></span>  
  
1.  <span data-ttu-id="7d574-116">No **Pesquisador de Objetos**, clique no sinal de adição para expandir o servidor que contém o alerta que você deseja excluir enviar para um pager.</span><span class="sxs-lookup"><span data-stu-id="7d574-116">In **Object Explorer**, click the plus sign to expand the server that contains the alert that you want to send to a pager.</span></span>  
  
2.  <span data-ttu-id="7d574-117">Clique com o botão direito do mouse em **SQL Server Agent** e selecione **Propriedades**</span><span class="sxs-lookup"><span data-stu-id="7d574-117">Right-click **SQL Server Agent** and select **Properties**</span></span>  
  
3.  <span data-ttu-id="7d574-118">Em **Selecione uma página**, selecione **Sistema de Alerta**.</span><span class="sxs-lookup"><span data-stu-id="7d574-118">Under **Select a page**, select **Alert System**.</span></span>  
  
4.  <span data-ttu-id="7d574-119">Nas caixas **Linha Para** e **Linha Cc** do campo **Formatação de endereço para emails por pager** , insira o prefixo ou sufixo de endereço de pager.</span><span class="sxs-lookup"><span data-stu-id="7d574-119">In the **To line** and **CC line** boxes of the **Address formatting for pager e-mails** field, enter the pager address prefix or suffix.</span></span> <span data-ttu-id="7d574-120">O endereço de pager atual do operador é inserido quando uma notificação é enviada.</span><span class="sxs-lookup"><span data-stu-id="7d574-120">The operator's actual pager address is inserted when a notification is sent.</span></span>  
  
5.  <span data-ttu-id="7d574-121">Na caixa **Assunto** , insira o prefixo ou sufixo de linha de assunto.</span><span class="sxs-lookup"><span data-stu-id="7d574-121">In the **Subject** box, enter the subject line prefix or suffix.</span></span>  
  
6.  <span data-ttu-id="7d574-122">Marque a caixa de seleção **Incluir corpo do email na página de notificação** para incluir a mensagem de email inteira na mensagem do pager (em vez de apenas a linha do assunto).</span><span class="sxs-lookup"><span data-stu-id="7d574-122">Select the **Include body of e-mail in notification page** check box to include the full e-mail message with the pager message (as opposed to the subject line only).</span></span>  
  
7.  <span data-ttu-id="7d574-123">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="7d574-123">When finished, click **OK**.</span></span>  
  
  
