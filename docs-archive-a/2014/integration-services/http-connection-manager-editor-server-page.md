---
title: Editor do Gerenciador de conexões HTTP (página servidor) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.httpconnection.server.f1
helpviewer_keywords:
- HTTP Connection Manager Editor
ms.assetid: 774778a0-ece6-4971-b93f-b121d8fc1fc1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a2349766b11b28ff258496dc966d554d49c7657b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570127"
---
# <a name="http-connection-manager-editor-server-page"></a><span data-ttu-id="d0d7d-102">Editor do Gerenciador de Conexões HTTP (página Servidor)</span><span class="sxs-lookup"><span data-stu-id="d0d7d-102">HTTP Connection Manager Editor (Server Page)</span></span>
  <span data-ttu-id="d0d7d-103">Use a guia **Servidor** da caixa de diálogo **Editor do Gerenciador de Conexões de HTTP** para configurar o Gerenciador de Conexões de HTTP especificando propriedades como URL e credenciais de segurança.</span><span class="sxs-lookup"><span data-stu-id="d0d7d-103">Use the **Server** tab of the **HTTP Connection Manager Editor** dialog box to configure the HTTP Connection Manager by specifying properties such as the URL and security credentials.</span></span> <span data-ttu-id="d0d7d-104">Uma conexão HTTP permite que um pacote acesse um servidor Web usando o HTTP para enviar ou receber arquivos.</span><span class="sxs-lookup"><span data-stu-id="d0d7d-104">An HTTP connection enables a package to access a Web server by using HTTP to send or receive files.</span></span> <span data-ttu-id="d0d7d-105">Depois de configurar o Gerenciador de Conexões de HTTP, você também pode testar a conexão.</span><span class="sxs-lookup"><span data-stu-id="d0d7d-105">After configuring the HTTP Connection Manager, you can also test the connection.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d0d7d-106">O gerenciador de conexões HTTP dá suporte apenas para autenticação anônima e autenticação básica.</span><span class="sxs-lookup"><span data-stu-id="d0d7d-106">The HTTP connection manager supports only anonymous authentication and basic authentication.</span></span> <span data-ttu-id="d0d7d-107">Ele não suporta a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="d0d7d-107">It does not support Windows Authentication.</span></span>  
  
 <span data-ttu-id="d0d7d-108">Para obter mais informações sobre o gerenciador de conexões de HTTP, consulte [HTTP Connection Manager](connection-manager/http-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="d0d7d-108">To learn more about the HTTP connection manager, see [HTTP Connection Manager](connection-manager/http-connection-manager.md).</span></span> <span data-ttu-id="d0d7d-109">Para saber mais sobre um cenário de utilização geral para o Gerenciador de Conexões de HTTP, consulte [Web Service Task](control-flow/web-service-task.md).</span><span class="sxs-lookup"><span data-stu-id="d0d7d-109">To learn more about a common usage scenario for the HTTP Connection Manager, see [Web Service Task](control-flow/web-service-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="d0d7d-110">Opções</span><span class="sxs-lookup"><span data-stu-id="d0d7d-110">Options</span></span>  
 <span data-ttu-id="d0d7d-111">**Servidor URL**</span><span class="sxs-lookup"><span data-stu-id="d0d7d-111">**Server URL**</span></span>  
 <span data-ttu-id="d0d7d-112">Digite o URL do servidor.</span><span class="sxs-lookup"><span data-stu-id="d0d7d-112">Type the URL for the server.</span></span>  
  
 <span data-ttu-id="d0d7d-113">Para usar o botão **Baixar WSDL** na página **Geral** do **Editor da Tarefa Serviço da Web** para baixar um arquivo WSDL, digite a URL do arquivo WSDL.</span><span class="sxs-lookup"><span data-stu-id="d0d7d-113">If you plan to use the **Download WSDL** button on the **General** page of the **Web Service Task Editor** to download a WSDL file, type the URL for the WSDL file.</span></span> <span data-ttu-id="d0d7d-114">Essa URL termina com "?wsdl".</span><span class="sxs-lookup"><span data-stu-id="d0d7d-114">This URL ends with "?wsdl".</span></span>  
  
 <span data-ttu-id="d0d7d-115">**Usar credenciais**</span><span class="sxs-lookup"><span data-stu-id="d0d7d-115">**Use credentials**</span></span>  
 <span data-ttu-id="d0d7d-116">Especifique se você o Gerenciador de Conexões de HTTP deve usar as credenciais de segurança do usuário para autenticação.</span><span class="sxs-lookup"><span data-stu-id="d0d7d-116">Specify whether you want the HTTP Connection Manager to use the user's security credentials for authentication.</span></span>  
  
 <span data-ttu-id="d0d7d-117">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="d0d7d-117">**User name**</span></span>  
 <span data-ttu-id="d0d7d-118">Se o Gerenciador de Conexões de HTTP usar credenciais, será necessário especificar um nome de usuário, senha e domínio.</span><span class="sxs-lookup"><span data-stu-id="d0d7d-118">If the HTTP Connection Manager uses credentials, you must specify a user name, password, and domain.</span></span>  
  
 <span data-ttu-id="d0d7d-119">**Senha**</span><span class="sxs-lookup"><span data-stu-id="d0d7d-119">**Password**</span></span>  
 <span data-ttu-id="d0d7d-120">Se o Gerenciador de Conexões de HTTP usar credenciais, será necessário especificar um nome de usuário, senha e domínio.</span><span class="sxs-lookup"><span data-stu-id="d0d7d-120">If the HTTP Connection Manager uses credentials, you must specify a user name, password, and domain.</span></span>  
  
 <span data-ttu-id="d0d7d-121">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="d0d7d-121">**Domain**</span></span>  
 <span data-ttu-id="d0d7d-122">Se o Gerenciador de Conexões de HTTP usar credenciais, será necessário especificar um nome de usuário, senha e domínio.</span><span class="sxs-lookup"><span data-stu-id="d0d7d-122">If the HTTP Connection Manager uses credentials, you must specify a user name, password, and domain.</span></span>  
  
 <span data-ttu-id="d0d7d-123">**Usar certificado do cliente**</span><span class="sxs-lookup"><span data-stu-id="d0d7d-123">**Use client certificate**</span></span>  
 <span data-ttu-id="d0d7d-124">Especifique se o Gerenciador de Conexões de HTTP deve usar um certificado do cliente para autenticação.</span><span class="sxs-lookup"><span data-stu-id="d0d7d-124">Specify whether you want the HTTP Connection Manager to use a client certificate for authentication.</span></span>  
  
 <span data-ttu-id="d0d7d-125">**Certificado**</span><span class="sxs-lookup"><span data-stu-id="d0d7d-125">**Certificate**</span></span>  
 <span data-ttu-id="d0d7d-126">Selecione um certificado na lista usando a caixa de diálogo **Selecionar Certificado** .</span><span class="sxs-lookup"><span data-stu-id="d0d7d-126">Select a certificate from the list by using the **Select Certificate** dialog box.</span></span> <span data-ttu-id="d0d7d-127">A caixa de texto exibe o nome associado a este certificado.</span><span class="sxs-lookup"><span data-stu-id="d0d7d-127">The text box displays the name associated with this certificate.</span></span>  
  
 <span data-ttu-id="d0d7d-128">**Tempo limite (em segundos)**</span><span class="sxs-lookup"><span data-stu-id="d0d7d-128">**Time-out (in seconds)**</span></span>  
 <span data-ttu-id="d0d7d-129">Forneça um tempo limite para conexão com o servidor Web.</span><span class="sxs-lookup"><span data-stu-id="d0d7d-129">Provide a time-out for connecting to the Web server.</span></span> <span data-ttu-id="d0d7d-130">O valor padrão desta propriedade é 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="d0d7d-130">The default value of this property is 30 seconds.</span></span>  
  
 <span data-ttu-id="d0d7d-131">**Tamanho da parte (em KB)**</span><span class="sxs-lookup"><span data-stu-id="d0d7d-131">**Chunk size (in KB)**</span></span>  
 <span data-ttu-id="d0d7d-132">Forneça um tamanho da parte para gravar dados.</span><span class="sxs-lookup"><span data-stu-id="d0d7d-132">Provide a chunk size for writing data.</span></span>  
  
 <span data-ttu-id="d0d7d-133">**Testar Conexão**</span><span class="sxs-lookup"><span data-stu-id="d0d7d-133">**Test Connection**</span></span>  
 <span data-ttu-id="d0d7d-134">Depois de configurar o Gerenciador de Conexões de HTTP, confirme se a conexão é viável clicando em **Testar Conexão**.</span><span class="sxs-lookup"><span data-stu-id="d0d7d-134">After configuring the HTTP Connection Manager, confirm that the connection is viable by clicking **Test Connection**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0d7d-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d0d7d-135">See Also</span></span>  
 <span data-ttu-id="d0d7d-136">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="d0d7d-136">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="d0d7d-137">Editor do Gerenciador de Conexões HTTP &#40;Página Proxy&#41;</span><span class="sxs-lookup"><span data-stu-id="d0d7d-137">HTTP Connection Manager Editor &#40;Proxy Page&#41;</span></span>](../../2014/integration-services/http-connection-manager-editor-proxy-page.md)  
  
  
