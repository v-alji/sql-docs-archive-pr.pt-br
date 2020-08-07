---
title: Editor do Gerenciador de conexões WMI | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.wmiconnection.f1
helpviewer_keywords:
- WMI Connection Manager Editor
ms.assetid: 0ef2c913-0779-4a07-989e-3361cd83170b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e85cdd2157c8ebe4cb9e6b53f8c3b47ff102a7b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582500"
---
# <a name="wmi-connection-manager-editor"></a><span data-ttu-id="033bd-102">Editor do Gerenciador de Conexões WMI</span><span class="sxs-lookup"><span data-stu-id="033bd-102">WMI Connection Manager Editor</span></span>
  <span data-ttu-id="033bd-103">Use a caixa de diálogo **Gerenciador de Conexões WMI** para especificar uma conexão WMI (Instrumentação de Gerenciamento do Windows) da Microsoft com um servidor.</span><span class="sxs-lookup"><span data-stu-id="033bd-103">Use the **WMI Connection Manager** dialog box to specify a Microsoft Windows Management Instrumentation (WMI) connection to a server.</span></span>  
  
 <span data-ttu-id="033bd-104">Para obter mais informações sobre o gerenciador de conexões WMI, consulte [WMI Connection Manager](connection-manager/wmi-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="033bd-104">To learn more about the WMI connection manager, see [WMI Connection Manager](connection-manager/wmi-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="033bd-105">Opções</span><span class="sxs-lookup"><span data-stu-id="033bd-105">Options</span></span>  
 <span data-ttu-id="033bd-106">**Nome**</span><span class="sxs-lookup"><span data-stu-id="033bd-106">**Name**</span></span>  
 <span data-ttu-id="033bd-107">Forneça um nome exclusivo para o gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="033bd-107">Provide a unique name for the connection manager.</span></span>  
  
 <span data-ttu-id="033bd-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="033bd-108">**Description**</span></span>  
 <span data-ttu-id="033bd-109">Descreva o gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="033bd-109">Describe the connection manager.</span></span> <span data-ttu-id="033bd-110">Como prática recomendável, descreva o gerenciador de conexões em termos de objetivo, para tornar os pacotes autodocumentados e mais fáceis de manter.</span><span class="sxs-lookup"><span data-stu-id="033bd-110">As a best practice, describe the connection manager in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="033bd-111">**Nome do servidor**</span><span class="sxs-lookup"><span data-stu-id="033bd-111">**Server name**</span></span>  
 <span data-ttu-id="033bd-112">Forneça o nome do servidor com o qual deseja fazer a conexão WMI.</span><span class="sxs-lookup"><span data-stu-id="033bd-112">Provide the name of the server to which you want to make the WMI connection.</span></span>  
  
 <span data-ttu-id="033bd-113">**Namespace**</span><span class="sxs-lookup"><span data-stu-id="033bd-113">**Namespace**</span></span>  
 <span data-ttu-id="033bd-114">Especifique o namespace WMI.</span><span class="sxs-lookup"><span data-stu-id="033bd-114">Specify the WMI namespace.</span></span>  
  
 <span data-ttu-id="033bd-115">**Usar autenticação do Windows**</span><span class="sxs-lookup"><span data-stu-id="033bd-115">**Use Windows authentication**</span></span>  
 <span data-ttu-id="033bd-116">Selecione para usar Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="033bd-116">Select to use Windows Authentication.</span></span> <span data-ttu-id="033bd-117">Se usar Autenticação do Windows, não será preciso fornecer um nome de usuário nem senha para a conexão.</span><span class="sxs-lookup"><span data-stu-id="033bd-117">If you use Windows Authentication, you do not need to provide a user name or password for the connection.</span></span>  
  
 <span data-ttu-id="033bd-118">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="033bd-118">**User name**</span></span>  
 <span data-ttu-id="033bd-119">Se não usar Autenticação do Windows, será preciso fornecer um nome de usuário para a conexão.</span><span class="sxs-lookup"><span data-stu-id="033bd-119">If you do not use Windows Authentication, you must provide a user name for the connection.</span></span>  
  
 <span data-ttu-id="033bd-120">**Senha**</span><span class="sxs-lookup"><span data-stu-id="033bd-120">**Password**</span></span>  
 <span data-ttu-id="033bd-121">Se não usar Autenticação do Windows, será preciso fornecer uma senha para a conexão.</span><span class="sxs-lookup"><span data-stu-id="033bd-121">If you do not use Windows Authentication, you must provide the password for the connection.</span></span>  
  
 <span data-ttu-id="033bd-122">**Test**</span><span class="sxs-lookup"><span data-stu-id="033bd-122">**Test**</span></span>  
 <span data-ttu-id="033bd-123">Teste as configurações do gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="033bd-123">Test the connection manager settings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="033bd-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="033bd-124">See Also</span></span>  
 <span data-ttu-id="033bd-125">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="033bd-125">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="033bd-126">[Provedor WMI para conceitos de gerenciamento de configuração](../relational-databases/wmi-provider-configuration/wmi-provider-for-configuration-management.md) </span><span class="sxs-lookup"><span data-stu-id="033bd-126">[WMI Provider for Configuration Management Concepts](../relational-databases/wmi-provider-configuration/wmi-provider-for-configuration-management.md) </span></span>  
 [<span data-ttu-id="033bd-127">Provedor WMI para conceitos de eventos de servidor</span><span class="sxs-lookup"><span data-stu-id="033bd-127">WMI Provider for Server Events Concepts</span></span>](../relational-databases/wmi-provider-server-events/wmi-provider-for-server-events-concepts.md)  
  
  
