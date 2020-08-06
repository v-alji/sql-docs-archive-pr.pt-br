---
title: Propriedades do alerta – novo alerta (página resposta) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.alert.response.f1
ms.assetid: 72daf008-f9ea-4077-b217-5048e7759d3e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 34e7f11ff3210ec4fc1835751bc35b140d3fa0ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683917"
---
# <a name="alert-properties-new-alert-response-page"></a><span data-ttu-id="8f80d-102">Propriedades do alerta – novo alerta (página resposta)</span><span class="sxs-lookup"><span data-stu-id="8f80d-102">Alert Properties-New Alert (Response Page)</span></span>
  <span data-ttu-id="8f80d-103">Use esta página para especificar um trabalho que você deseja executar e para obter uma lista de operadores a serem notificados em resposta a um [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alerta do Agent.</span><span class="sxs-lookup"><span data-stu-id="8f80d-103">Use this page to specify a job that you want to run and to obtain a list of operators to be notified in response to a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8f80d-104">Opções</span><span class="sxs-lookup"><span data-stu-id="8f80d-104">Options</span></span>  
 <span data-ttu-id="8f80d-105">**Executar trabalho**</span><span class="sxs-lookup"><span data-stu-id="8f80d-105">**Execute job**</span></span>  
 <span data-ttu-id="8f80d-106">Habilita as opções **Lista de trabalhos**, **Novo trabalho** e **Exibir trabalho** .</span><span class="sxs-lookup"><span data-stu-id="8f80d-106">Enables the **Job list**, **New job** and **View job** options.</span></span>  
  
 <span data-ttu-id="8f80d-107">**Novo trabalho**</span><span class="sxs-lookup"><span data-stu-id="8f80d-107">**New job**</span></span>  
 <span data-ttu-id="8f80d-108">Abra a caixa de diálogo **Novo Trabalho** .</span><span class="sxs-lookup"><span data-stu-id="8f80d-108">Open the **New Job** dialog box.</span></span> <span data-ttu-id="8f80d-109">Esse botão não está disponível quando **Executar trabalho** não está selecionado.</span><span class="sxs-lookup"><span data-stu-id="8f80d-109">This button is not available when **Execute job** is not selected.</span></span>  
  
 <span data-ttu-id="8f80d-110">**Exibir trabalho**</span><span class="sxs-lookup"><span data-stu-id="8f80d-110">**View job**</span></span>  
 <span data-ttu-id="8f80d-111">Exiba ou modifique o trabalho selecionado.</span><span class="sxs-lookup"><span data-stu-id="8f80d-111">View or modify the selected job.</span></span> <span data-ttu-id="8f80d-112">Essa opção não está disponível quando **Executar trabalho** não está selecionado.</span><span class="sxs-lookup"><span data-stu-id="8f80d-112">This option is not available when **Execute job** is not selected.</span></span>  
  
 <span data-ttu-id="8f80d-113">**Notificar operadores**</span><span class="sxs-lookup"><span data-stu-id="8f80d-113">**Notify operators**</span></span>  
 <span data-ttu-id="8f80d-114">Habilita os controles que permitem adicionar, remover ou alterar operadores.</span><span class="sxs-lookup"><span data-stu-id="8f80d-114">Enables the controls that allow you to add, remove, or change operators.</span></span>  
  
 <span data-ttu-id="8f80d-115">**Lista de operadores**</span><span class="sxs-lookup"><span data-stu-id="8f80d-115">**Operator list**</span></span>  
 <span data-ttu-id="8f80d-116">Lista os operadores a notificar quando ocorrer um alerta.</span><span class="sxs-lookup"><span data-stu-id="8f80d-116">Lists the operators to notify when an alert occurs.</span></span> <span data-ttu-id="8f80d-117">Para especificar um método de notificação, marque a caixa de seleção **Email**, **Pager**ou **Net send** que é exibida depois do nome do operador. Essa opção não está disponível quando **Notificar operadores** não está selecionado.</span><span class="sxs-lookup"><span data-stu-id="8f80d-117">To specify a notification method, select the **E-mail**, **Pager**, or **Net send** check box that is displayed after the operator name.This option not available when **Notify operators** is not selected.</span></span>  
  
 <span data-ttu-id="8f80d-118">**Mensagens**</span><span class="sxs-lookup"><span data-stu-id="8f80d-118">**E-mail**</span></span>  
 <span data-ttu-id="8f80d-119">Use email para notificar o operador.</span><span class="sxs-lookup"><span data-stu-id="8f80d-119">Use e-mail to notify the operator.</span></span>  
  
 <span data-ttu-id="8f80d-120">**Pager**</span><span class="sxs-lookup"><span data-stu-id="8f80d-120">**Pager**</span></span>  
 <span data-ttu-id="8f80d-121">Use o endereço de email do pager para notificar o operador.</span><span class="sxs-lookup"><span data-stu-id="8f80d-121">Use the pager e-mail address to notify the operator.</span></span>  
  
 <span data-ttu-id="8f80d-122">**Net send**</span><span class="sxs-lookup"><span data-stu-id="8f80d-122">**Net send**</span></span>  
 <span data-ttu-id="8f80d-123">Use **net send** para notificar o operador.</span><span class="sxs-lookup"><span data-stu-id="8f80d-123">Use **net send** to notify the operator.</span></span>  
  
 <span data-ttu-id="8f80d-124">**Novo operador**</span><span class="sxs-lookup"><span data-stu-id="8f80d-124">**New operator**</span></span>  
 <span data-ttu-id="8f80d-125">Exibe a caixa de diálogo **Novo Operador** que você pode usar para criar um operador novo.</span><span class="sxs-lookup"><span data-stu-id="8f80d-125">Displays the **New Operator** dialog box, which you can use to create a new operator.</span></span>  
  
 <span data-ttu-id="8f80d-126">**Exibir operador**</span><span class="sxs-lookup"><span data-stu-id="8f80d-126">**View operator**</span></span>  
 <span data-ttu-id="8f80d-127">Exibe a caixa de diálogo **Propriedades** para o operador selecionado atualmente.</span><span class="sxs-lookup"><span data-stu-id="8f80d-127">Displays the **Properties** dialog box for the currently selected operator.</span></span> <span data-ttu-id="8f80d-128">Você pode exibir e modificar as propriedades do operador na caixa de diálogo **Propriedades do Operador**.</span><span class="sxs-lookup"><span data-stu-id="8f80d-128">You can view and modified operator properties on the **Operator Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f80d-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8f80d-129">See Also</span></span>  
 <span data-ttu-id="8f80d-130">[Alerts](alerts.md) </span><span class="sxs-lookup"><span data-stu-id="8f80d-130">[Alerts](alerts.md) </span></span>  
 <span data-ttu-id="8f80d-131">[Criar um alerta usando o nível de severidade](create-an-alert-using-severity-level.md) </span><span class="sxs-lookup"><span data-stu-id="8f80d-131">[Create an Alert Using Severity Level](create-an-alert-using-severity-level.md) </span></span>  
 <span data-ttu-id="8f80d-132">[Alerts](alerts.md) </span><span class="sxs-lookup"><span data-stu-id="8f80d-132">[Alerts](alerts.md) </span></span>  
 <span data-ttu-id="8f80d-133">[Editar um alerta](edit-an-alert.md) </span><span class="sxs-lookup"><span data-stu-id="8f80d-133">[Edit an Alert](edit-an-alert.md) </span></span>  
 [<span data-ttu-id="8f80d-134">Delete an Alert</span><span class="sxs-lookup"><span data-stu-id="8f80d-134">Delete an Alert</span></span>](delete-an-alert.md)  
  
  
