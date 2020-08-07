---
title: Propriedades do servidor de relatório (guia Logon) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: f54be594-f290-4db2-bf18-fd2521728a4a
author: stevestein
ms.author: sstein
ms.openlocfilehash: a2fca58ee9b419613bc8f1dbd325481efc9069c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575474"
---
# <a name="report-server-properties-log-on-tab"></a><span data-ttu-id="67261-102">Propriedades do servidor de relatório (guia Fazer Logon)</span><span class="sxs-lookup"><span data-stu-id="67261-102">Report Server Properties (Log On Tab)</span></span>
  <span data-ttu-id="67261-103">Use a guia **Fazer Logon** da caixa de diálogo **Propriedades de Servidor de Relatório** para especificar a conta usada pelo serviço Servidor de Relatório e para iniciar e parar o serviço.</span><span class="sxs-lookup"><span data-stu-id="67261-103">Use the **Log On** tab of the **Report Server Properties** dialog box to specify the account used by the Report Server service, and to start and stop the service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="67261-104">Opções</span><span class="sxs-lookup"><span data-stu-id="67261-104">Options</span></span>  
 <span data-ttu-id="67261-105">**Conta Sistema Local**</span><span class="sxs-lookup"><span data-stu-id="67261-105">**Local System account**</span></span>  
 <span data-ttu-id="67261-106">Especifique uma conta Sistema Local que não requeira uma senha.</span><span class="sxs-lookup"><span data-stu-id="67261-106">Specify a local system account, which does not require a password.</span></span> <span data-ttu-id="67261-107">Porém, essa conta pode restringir a interação do serviço com outros servidores, dependendo dos privilégios concedidos a ela.</span><span class="sxs-lookup"><span data-stu-id="67261-107">However, the local system account may restrict the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="67261-108">**Esta conta**</span><span class="sxs-lookup"><span data-stu-id="67261-108">**This account**</span></span>  
 <span data-ttu-id="67261-109">Especifique uma conta de usuário local ou de domínio que usa a Autenticação do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="67261-109">Specify a local or domain user account that uses [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="67261-110">recomenda usar uma conta de usuário do domínio com direitos mínimos para serviços.</span><span class="sxs-lookup"><span data-stu-id="67261-110">recommends using a domain user account with minimal rights for services.</span></span> <span data-ttu-id="67261-111">Para obter informações sobre como selecionar uma conta, pesquise o tópico "Configurando as contas de serviço do Windows" nos Manuais Online.</span><span class="sxs-lookup"><span data-stu-id="67261-111">For information about selecting an account, search Books Online for the topic Setting Up Windows Service Accounts.</span></span>  
  
 <span data-ttu-id="67261-112">**Nome da Conta**</span><span class="sxs-lookup"><span data-stu-id="67261-112">**Account Name**</span></span>  
 <span data-ttu-id="67261-113">Especifique o nome da conta local ou de usuário de domínio.</span><span class="sxs-lookup"><span data-stu-id="67261-113">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="67261-114">**Senha**</span><span class="sxs-lookup"><span data-stu-id="67261-114">**Password**</span></span>  
 <span data-ttu-id="67261-115">Digite a senha da conta.</span><span class="sxs-lookup"><span data-stu-id="67261-115">Type the password of the account.</span></span>  
  
 <span data-ttu-id="67261-116">**Confirmar senha**</span><span class="sxs-lookup"><span data-stu-id="67261-116">**Confirm password**</span></span>  
 <span data-ttu-id="67261-117">Digite a senha da conta novamente.</span><span class="sxs-lookup"><span data-stu-id="67261-117">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="67261-118">**Iniciar**</span><span class="sxs-lookup"><span data-stu-id="67261-118">**Start**</span></span>  
 <span data-ttu-id="67261-119">Inicie o serviço.</span><span class="sxs-lookup"><span data-stu-id="67261-119">Start the service.</span></span>  
  
 <span data-ttu-id="67261-120">**Parar**</span><span class="sxs-lookup"><span data-stu-id="67261-120">**Stop**</span></span>  
 <span data-ttu-id="67261-121">Parar o serviço.</span><span class="sxs-lookup"><span data-stu-id="67261-121">Stop the service.</span></span>  
  
 <span data-ttu-id="67261-122">**Pausar**</span><span class="sxs-lookup"><span data-stu-id="67261-122">**Pause**</span></span>  
 <span data-ttu-id="67261-123">Pausar o serviço.</span><span class="sxs-lookup"><span data-stu-id="67261-123">Pause the service.</span></span>  
  
 <span data-ttu-id="67261-124">**Retomar**</span><span class="sxs-lookup"><span data-stu-id="67261-124">**Resume**</span></span>  
 <span data-ttu-id="67261-125">Retomar um serviço pausado.</span><span class="sxs-lookup"><span data-stu-id="67261-125">Resume a paused service.</span></span>  
  
  
