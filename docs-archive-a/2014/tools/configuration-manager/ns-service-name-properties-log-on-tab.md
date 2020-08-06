---
title: Propriedades do NS $ &lt; Service Name &gt; (guia fazer logon) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 5e6816ec-d4c5-4429-8033-b97427584890
author: stevestein
ms.author: sstein
ms.openlocfilehash: b175895f2385717a67642a41a44dc0d47a1d8d92
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683862"
---
# <a name="nsltservice-namegt-properties-log-on-tab"></a><span data-ttu-id="a71c3-102">Propriedades do NS$&lt;nome do serviço&gt; (guia Logon)</span><span class="sxs-lookup"><span data-stu-id="a71c3-102">NS$&lt;service name&gt; Properties (Log On Tab)</span></span>
  <span data-ttu-id="a71c3-103">Use a guia **Fazer Logon** da caixa de diálogo **Propriedades de Notification Services** para especificar a conta usada pelo serviço [!INCLUDE[ssNS](../../includes/ssns-md.md)] e para iniciar e parar o serviço.</span><span class="sxs-lookup"><span data-stu-id="a71c3-103">Use the **Log On** tab of the **Notification Services Properties** dialog box to specify the account used by the [!INCLUDE[ssNS](../../includes/ssns-md.md)] service, and to start and stop the service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a71c3-104">Opções</span><span class="sxs-lookup"><span data-stu-id="a71c3-104">Options</span></span>  
 <span data-ttu-id="a71c3-105">**Conta Sistema Local**</span><span class="sxs-lookup"><span data-stu-id="a71c3-105">**Local System account**</span></span>  
 <span data-ttu-id="a71c3-106">Especifique uma conta Sistema Local que não requeira uma senha.</span><span class="sxs-lookup"><span data-stu-id="a71c3-106">Specify a local system account, which does not require a password.</span></span> <span data-ttu-id="a71c3-107">Porém, essa conta pode restringir a interação do serviço com outros servidores, dependendo dos privilégios concedidos a ela.</span><span class="sxs-lookup"><span data-stu-id="a71c3-107">However, the local system account may restrict the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="a71c3-108">**Esta conta**</span><span class="sxs-lookup"><span data-stu-id="a71c3-108">**This account**</span></span>  
 <span data-ttu-id="a71c3-109">Especifique uma conta de usuário local ou de domínio que usa a Autenticação do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="a71c3-109">Specify a local or domain user account that uses [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="a71c3-110">recomenda usar uma conta de usuário do domínio com direitos mínimos para serviços.</span><span class="sxs-lookup"><span data-stu-id="a71c3-110">recommends using a domain user account with minimal rights for services.</span></span> <span data-ttu-id="a71c3-111">Para obter informações sobre como selecionar uma conta, pesquise o tópico "Configurando as contas de serviço do Windows" nos Manuais Online.</span><span class="sxs-lookup"><span data-stu-id="a71c3-111">For information about selecting an account, search Books Online for the topic, "Setting Up Windows Service Accounts."</span></span>  
  
 <span data-ttu-id="a71c3-112">**Nome da Conta**</span><span class="sxs-lookup"><span data-stu-id="a71c3-112">**Account Name**</span></span>  
 <span data-ttu-id="a71c3-113">Especifique o nome da conta local ou de usuário de domínio.</span><span class="sxs-lookup"><span data-stu-id="a71c3-113">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="a71c3-114">**Senha**</span><span class="sxs-lookup"><span data-stu-id="a71c3-114">**Password**</span></span>  
 <span data-ttu-id="a71c3-115">Digite a senha da conta.</span><span class="sxs-lookup"><span data-stu-id="a71c3-115">Type the password of the account.</span></span>  
  
 <span data-ttu-id="a71c3-116">**Confirmar senha**</span><span class="sxs-lookup"><span data-stu-id="a71c3-116">**Confirm password**</span></span>  
 <span data-ttu-id="a71c3-117">Digite a senha da conta novamente.</span><span class="sxs-lookup"><span data-stu-id="a71c3-117">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="a71c3-118">**Iniciar**</span><span class="sxs-lookup"><span data-stu-id="a71c3-118">**Start**</span></span>  
 <span data-ttu-id="a71c3-119">Inicie o serviço.</span><span class="sxs-lookup"><span data-stu-id="a71c3-119">Start the service.</span></span>  
  
 <span data-ttu-id="a71c3-120">**Parar**</span><span class="sxs-lookup"><span data-stu-id="a71c3-120">**Stop**</span></span>  
 <span data-ttu-id="a71c3-121">Parar o serviço.</span><span class="sxs-lookup"><span data-stu-id="a71c3-121">Stop the service.</span></span>  
  
 <span data-ttu-id="a71c3-122">**Pausar**</span><span class="sxs-lookup"><span data-stu-id="a71c3-122">**Pause**</span></span>  
 <span data-ttu-id="a71c3-123">Pausar o serviço.</span><span class="sxs-lookup"><span data-stu-id="a71c3-123">Pause the service.</span></span>  
  
 <span data-ttu-id="a71c3-124">**Retomar**</span><span class="sxs-lookup"><span data-stu-id="a71c3-124">**Resume**</span></span>  
 <span data-ttu-id="a71c3-125">Retomar um serviço pausado.</span><span class="sxs-lookup"><span data-stu-id="a71c3-125">Resume a paused service.</span></span>  
  
  
