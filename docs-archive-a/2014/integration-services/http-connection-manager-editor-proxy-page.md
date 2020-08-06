---
title: Editor do Gerenciador de conexões de HTTP (página proxy) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.httpconnection.proxy.f1
helpviewer_keywords:
- HTTP Connection Manager Editor
ms.assetid: e831a830-49a3-49c5-8a31-9731fc4fd12e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f8269dbbeb226ffa3f56c226e1a416d99c1e3f13
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570132"
---
# <a name="http-connection-manager-editor-proxy-page"></a><span data-ttu-id="febc2-102">Editor do Gerenciador de Conexões de HTTP (Página Proxy)</span><span class="sxs-lookup"><span data-stu-id="febc2-102">HTTP Connection Manager Editor (Proxy Page)</span></span>
  <span data-ttu-id="febc2-103">Use a guia **Proxy** da caixa de diálogo **Editor do Gerenciador de Conexões de HTTP** para configurar o Gerenciador de Conexões de HTTP para usar um servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="febc2-103">Use the **Proxy** tab of the **HTTP Connection Manager Editor** dialog box to configure the HTTP Connection Manager to use a proxy server.</span></span> <span data-ttu-id="febc2-104">Uma conexão HTTP permite que um pacote acesse um servidor Web usando o HTTP para enviar ou receber arquivos.</span><span class="sxs-lookup"><span data-stu-id="febc2-104">An HTTP connection enables a package to access a Web server by using HTTP to send or receive files.</span></span>  
  
 <span data-ttu-id="febc2-105">Para obter mais informações sobre o gerenciador de conexões de HTTP, consulte [HTTP Connection Manager](connection-manager/http-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="febc2-105">To learn more about the HTTP connection manager, see [HTTP Connection Manager](connection-manager/http-connection-manager.md).</span></span> <span data-ttu-id="febc2-106">Para saber mais sobre um cenário de utilização geral para o Gerenciador de Conexões de HTTP, consulte [Web Service Task](control-flow/web-service-task.md).</span><span class="sxs-lookup"><span data-stu-id="febc2-106">To learn more about a common usage scenario for the HTTP Connection Manager, see [Web Service Task](control-flow/web-service-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="febc2-107">Opções</span><span class="sxs-lookup"><span data-stu-id="febc2-107">Options</span></span>  
 <span data-ttu-id="febc2-108">**Usar proxy**</span><span class="sxs-lookup"><span data-stu-id="febc2-108">**Use proxy**</span></span>  
 <span data-ttu-id="febc2-109">Especifique se você quer que o Gerenciador de Conexões de HTTP conecte por de um servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="febc2-109">Specify whether you want the HTTP Connection Manager to connect through a proxy server.</span></span>  
  
 <span data-ttu-id="febc2-110">**URL do Proxy**</span><span class="sxs-lookup"><span data-stu-id="febc2-110">**Proxy URL**</span></span>  
 <span data-ttu-id="febc2-111">Digite a URL para o servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="febc2-111">Type the URL for the proxy server.</span></span>  
  
 <span data-ttu-id="febc2-112">**Ignorar proxy no local**</span><span class="sxs-lookup"><span data-stu-id="febc2-112">**Bypass proxy on local**</span></span>  
 <span data-ttu-id="febc2-113">Especifique se você quer que o Gerenciador de Conexões de HTTP ignore o servidor proxy para endereços locais.</span><span class="sxs-lookup"><span data-stu-id="febc2-113">Specify whether you want the HTTP Connection Manager to bypass the proxy server for local addresses.</span></span>  
  
 <span data-ttu-id="febc2-114">**Usar credenciais**</span><span class="sxs-lookup"><span data-stu-id="febc2-114">**Use credentials**</span></span>  
 <span data-ttu-id="febc2-115">Especifique se você quer que o Gerenciador de Conexões de HTTP use credenciais de segurança para o servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="febc2-115">Specify whether you want the HTTP Connection Manager to use security credentials for the proxy server.</span></span>  
  
 <span data-ttu-id="febc2-116">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="febc2-116">**User name**</span></span>  
 <span data-ttu-id="febc2-117">Se o Gerenciador de Conexões de HTTP usar credenciais, será necessário especificar um nome de usuário, senha e domínio.</span><span class="sxs-lookup"><span data-stu-id="febc2-117">If the HTTP Connection Manager uses credentials, you must specify a user name, password, and domain.</span></span>  
  
 <span data-ttu-id="febc2-118">**Senha**</span><span class="sxs-lookup"><span data-stu-id="febc2-118">**Password**</span></span>  
 <span data-ttu-id="febc2-119">Se o Gerenciador de Conexões de HTTP usar credenciais, será necessário especificar um nome de usuário, senha e domínio.</span><span class="sxs-lookup"><span data-stu-id="febc2-119">If the HTTP Connection Manager uses credentials, you must specify a user name, password, and domain.</span></span>  
  
 <span data-ttu-id="febc2-120">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="febc2-120">**Domain**</span></span>  
 <span data-ttu-id="febc2-121">Se o Gerenciador de Conexões de HTTP usar credenciais, será necessário especificar um nome de usuário, senha e domínio.</span><span class="sxs-lookup"><span data-stu-id="febc2-121">If the HTTP Connection Manager uses credentials, you must specify a user name, password, and domain.</span></span>  
  
 <span data-ttu-id="febc2-122">**Lista proxies ignoráveis**</span><span class="sxs-lookup"><span data-stu-id="febc2-122">**Proxy bypass list**</span></span>  
 <span data-ttu-id="febc2-123">A lista de endereços para os quais você quer ignorar o servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="febc2-123">The list of addresses for which  you want to bypass the proxy server.</span></span>  
  
 <span data-ttu-id="febc2-124">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="febc2-124">**Add**</span></span>  
 <span data-ttu-id="febc2-125">Digite um endereço para o qual você quer ignorar o servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="febc2-125">Type an address for which you want to bypass the proxy server.</span></span>  
  
 <span data-ttu-id="febc2-126">**Remover**</span><span class="sxs-lookup"><span data-stu-id="febc2-126">**Remove**</span></span>  
 <span data-ttu-id="febc2-127">Selecione um endereço e remova-o clicando em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="febc2-127">Select an address, and then remove it by clicking **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="febc2-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="febc2-128">See Also</span></span>  
 <span data-ttu-id="febc2-129">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="febc2-129">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="febc2-130">Editor do Gerenciador de Conexões HTTP &#40;Página Servidor&#41;</span><span class="sxs-lookup"><span data-stu-id="febc2-130">HTTP Connection Manager Editor &#40;Server Page&#41;</span></span>](../../2014/integration-services/http-connection-manager-editor-server-page.md)  
  
  
