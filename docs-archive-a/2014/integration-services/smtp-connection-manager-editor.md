---
title: Editor do Gerenciador de conexões SMTP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.smtpconnection.f1
helpviewer_keywords:
- SMTP Connection Manager Editor
ms.assetid: 2693de0d-b04d-4325-a856-ce667d2b8aa1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e14ed49f64b9faca40f575fc6760a8d25c0d4573
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685820"
---
# <a name="smtp-connection-manager-editor"></a><span data-ttu-id="c0bb6-102">Editor do Gerenciador de Conexões SMTP</span><span class="sxs-lookup"><span data-stu-id="c0bb6-102">SMTP Connection Manager Editor</span></span>
  <span data-ttu-id="c0bb6-103">Use a caixa de diálogo **Editor do Gerenciador de Conexões SMTP** para especificar um servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="c0bb6-103">Use the **SMTP Connection Manager Editor** dialog box to specify a Simple Mail Transfer Protocol (SMTP) server.</span></span>  
  
 <span data-ttu-id="c0bb6-104">Para saber mais sobre o Gerenciador de Conexões SMTP, consulte [SMTP Connection Manager](connection-manager/smtp-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="c0bb6-104">To learn more about the SMTP connection manager, see [SMTP Connection Manager](connection-manager/smtp-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="c0bb6-105">Opções</span><span class="sxs-lookup"><span data-stu-id="c0bb6-105">Options</span></span>  
 <span data-ttu-id="c0bb6-106">**Nome**</span><span class="sxs-lookup"><span data-stu-id="c0bb6-106">**Name**</span></span>  
 <span data-ttu-id="c0bb6-107">Forneça um nome exclusivo para o gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="c0bb6-107">Provide a unique name for the connection manager.</span></span>  
  
 <span data-ttu-id="c0bb6-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="c0bb6-108">**Description**</span></span>  
 <span data-ttu-id="c0bb6-109">Descreva o gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="c0bb6-109">Describe the connection manager.</span></span> <span data-ttu-id="c0bb6-110">Como prática recomendável, descreva o gerenciador de conexões em termos de objetivo, para tornar os pacotes autodocumentados e mais fáceis de manter.</span><span class="sxs-lookup"><span data-stu-id="c0bb6-110">As a best practice, describe the connection manager in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="c0bb6-111">**Servidor SMTP**</span><span class="sxs-lookup"><span data-stu-id="c0bb6-111">**SMTP server**</span></span>  
 <span data-ttu-id="c0bb6-112">Forneça o nome do servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="c0bb6-112">Provide the name of the SMTP server.</span></span>  
  
 <span data-ttu-id="c0bb6-113">**Usar Autenticação do Windows**</span><span class="sxs-lookup"><span data-stu-id="c0bb6-113">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="c0bb6-114">Selecione para enviar email usando um servidor SMTP que usa a Autenticação do Windows para autenticar o acesso ao servidor.</span><span class="sxs-lookup"><span data-stu-id="c0bb6-114">Select to send mail using an SMTP server that uses Windows Authentication to authenticate access to the server.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c0bb6-115">O gerenciador de conexões SMTP dá suporte apenas para autenticação anônima e Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="c0bb6-115">The SMTP connection manager supports only anonymous authentication and Windows Authentication.</span></span> <span data-ttu-id="c0bb6-116">Ele não suporta a autenticação básica.</span><span class="sxs-lookup"><span data-stu-id="c0bb6-116">It does not support basic authentication.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c0bb6-117">Ao usar o Microsoft Exchange como servidor SMTP, talvez seja necessário definir **usar a autenticação do Windows** para o `True` .</span><span class="sxs-lookup"><span data-stu-id="c0bb6-117">When using Microsoft Exchange as the SMTP server, you may need to set **Use Windows Authentication** to `True`.</span></span> <span data-ttu-id="c0bb6-118">Os servidores do Exchange podem ser configurados para não permitir conexões SMTP não autenticadas.</span><span class="sxs-lookup"><span data-stu-id="c0bb6-118">Exchange servers may be configured to disallow unauthenticated SMTP connections.</span></span>  
  
 <span data-ttu-id="c0bb6-119">**Habilitar SSL (Secure Sockets Layer)**</span><span class="sxs-lookup"><span data-stu-id="c0bb6-119">**Enable Secure Sockets Layer (SSL)**</span></span>  
 <span data-ttu-id="c0bb6-120">Selecione para criptografar a comunicação utilizando a SSL (Secure Sockets Layer) ao enviar mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="c0bb6-120">Select to encrypt communication using Secure Sockets Layer (SSL) when sending e-mail messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0bb6-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c0bb6-121">See Also</span></span>  
 [<span data-ttu-id="c0bb6-122">Referência de mensagens e erros do Integration Services</span><span class="sxs-lookup"><span data-stu-id="c0bb6-122">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
