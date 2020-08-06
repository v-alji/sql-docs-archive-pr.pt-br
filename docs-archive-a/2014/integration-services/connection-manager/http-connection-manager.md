---
title: Gerenciador de conexões HTTP | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- HTTP connection manager
- Web site connections [Integration Services]
- connection managers [Integration Services], HTTP
- Web server connections [Integration Services]
- connections [Integration Services], HTTP
ms.assetid: 26b2b3e1-d02c-46ca-8d31-7aef2bbc3c53
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 10c9f0778faa25aff8db4ad54ecaa8d3ccc5b359
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684820"
---
# <a name="http-connection-manager"></a><span data-ttu-id="d3172-102">Gerenciador de conexões HTTP</span><span class="sxs-lookup"><span data-stu-id="d3172-102">HTTP Connection Manager</span></span>
  <span data-ttu-id="d3172-103">Uma conexão HTTP permite que um pacote acesse um servidor Web usando o HTTP para enviar ou receber arquivos.</span><span class="sxs-lookup"><span data-stu-id="d3172-103">An HTTP connection enables a package to access a Web server by using HTTP to send or receive files.</span></span> <span data-ttu-id="d3172-104">A tarefa Serviço Web incluída no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] usa esse gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="d3172-104">The Web Service task that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes uses this connection manager.</span></span>  
  
 <span data-ttu-id="d3172-105">Quando você adiciona um gerenciador de conexões HTTP a um pacote, o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] cria um gerenciador de conexões que resolverá uma conexão HTTP em tempo de execução, define as propriedades do gerenciador de conexões e adiciona o gerenciador de conexões à coleção `Connections` no pacote.</span><span class="sxs-lookup"><span data-stu-id="d3172-105">When you add an HTTP connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to an HTTP connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span>  
  
 <span data-ttu-id="d3172-106">A propriedade `ConnectionManagerType` do gerenciador de conexões está definida como `HTTP.`</span><span class="sxs-lookup"><span data-stu-id="d3172-106">The `ConnectionManagerType` property of the connection manager is set to `HTTP.`</span></span>  
  
 <span data-ttu-id="d3172-107">Você pode configurar um gerenciador de conexões HTTP das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="d3172-107">You can configure the HTTP connection manager the following ways:</span></span>  
  
-   <span data-ttu-id="d3172-108">Use credenciais.</span><span class="sxs-lookup"><span data-stu-id="d3172-108">Use credentials.</span></span> <span data-ttu-id="d3172-109">Se o gerenciador de conexões HTTP usar credenciais, suas propriedades incluirão o nome de usuário, a senha e o domínio.</span><span class="sxs-lookup"><span data-stu-id="d3172-109">If the connection manager uses credentials, its properties include the user name, password, and domain.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="d3172-110">O gerenciador de conexões HTTP dá suporte apenas para autenticação anônima e autenticação básica.</span><span class="sxs-lookup"><span data-stu-id="d3172-110">The HTTP connection manager supports only anonymous authentication and basic authentication.</span></span> <span data-ttu-id="d3172-111">Ele não suporta a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="d3172-111">It does not support Windows Authentication.</span></span>  
  
-   <span data-ttu-id="d3172-112">Use um certificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="d3172-112">Use a client certificate.</span></span> <span data-ttu-id="d3172-113">Se o gerenciador de conexões usar um certificado do cliente, suas propriedades incluirão o nome de certificado.</span><span class="sxs-lookup"><span data-stu-id="d3172-113">If the connection manager uses a client certificate, its properties include the certificate name.</span></span>  
  
-   <span data-ttu-id="d3172-114">Forneça um tempo limite para conexão com o servidor e um tamanho da parte para gravar dados.</span><span class="sxs-lookup"><span data-stu-id="d3172-114">Provide a time-out for connecting to the server and a chunk size for writing data.</span></span>  
  
-   <span data-ttu-id="d3172-115">Use um servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="d3172-115">Use a proxy server.</span></span> <span data-ttu-id="d3172-116">O servidor proxy também pode ser configurado para usar credenciais e ignorar o servidor proxy com o uso de endereços locais em seu lugar.</span><span class="sxs-lookup"><span data-stu-id="d3172-116">The proxy server can also be configured to use credentials and to bypass the proxy server and use local addresses instead.</span></span>  
  
## <a name="configuration-of-the-http-connection-manager"></a><span data-ttu-id="d3172-117">Configuração do gerenciador de conexões HTTP</span><span class="sxs-lookup"><span data-stu-id="d3172-117">Configuration of the HTTP Connection Manager</span></span>  
 <span data-ttu-id="d3172-118">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="d3172-118">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="d3172-119">Para obter mais informações sobre as propriedades que podem ser definidas no [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="d3172-119">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="d3172-120">Editor do Gerenciador de Conexões HTTP &#40;Página Servidor&#41;</span><span class="sxs-lookup"><span data-stu-id="d3172-120">HTTP Connection Manager Editor &#40;Server Page&#41;</span></span>](../http-connection-manager-editor-server-page.md)  
  
-   [<span data-ttu-id="d3172-121">Editor do Gerenciador de Conexões HTTP &#40;Página Proxy&#41;</span><span class="sxs-lookup"><span data-stu-id="d3172-121">HTTP Connection Manager Editor &#40;Proxy Page&#41;</span></span>](../http-connection-manager-editor-proxy-page.md)  
  
 <span data-ttu-id="d3172-122">Para obter informações sobre como configurar um gerenciador de conexões de forma programática, consulte <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>.</span><span class="sxs-lookup"><span data-stu-id="d3172-122">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3172-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d3172-123">See Also</span></span>  
 <span data-ttu-id="d3172-124">[Tarefa serviço Web](../control-flow/web-service-task.md) </span><span class="sxs-lookup"><span data-stu-id="d3172-124">[Web Service Task](../control-flow/web-service-task.md) </span></span>  
 [<span data-ttu-id="d3172-125">Conexões do SSIS &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d3172-125">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
