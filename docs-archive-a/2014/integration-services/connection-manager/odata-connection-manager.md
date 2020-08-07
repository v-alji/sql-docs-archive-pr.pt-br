---
title: Gerenciador de Conexões OData | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 3caa4372-aff3-4c0f-9ecd-97870948b8d0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 46eedaa008b284661fd1d364d2e2bc87c373a9f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575270"
---
# <a name="odata-connection-manager"></a><span data-ttu-id="55017-102">Gerenciador de conexões do OData</span><span class="sxs-lookup"><span data-stu-id="55017-102">OData Connection Manager</span></span>
  <span data-ttu-id="55017-103">Um gerenciador de conexões OData habilita um pacote a conectar-se a uma fonte OData.</span><span class="sxs-lookup"><span data-stu-id="55017-103">An OData connection manager enables a package to connect to an OData source.</span></span> <span data-ttu-id="55017-104">Um componente de origem OData se conecta a uma origem OData usando um gerenciador de conexões OData e consome dados do serviço.</span><span class="sxs-lookup"><span data-stu-id="55017-104">An OData Source component connects to an OData source using an OData connection manager and consumes data from the service.</span></span> <span data-ttu-id="55017-105">Consulte a seção [OData Source](../data-flow/odata-source.md)para obter informações detalhadas, inclusive as instruções de instalação desses componentes.</span><span class="sxs-lookup"><span data-stu-id="55017-105">See [OData Source](../data-flow/odata-source.md)section for detailed information including the installation instructions for these components.</span></span>  
  
## <a name="adding-connection-manager-to-an-ssis-package"></a><span data-ttu-id="55017-106">Adicionando o gerenciador de conexões a um pacote SSIS</span><span class="sxs-lookup"><span data-stu-id="55017-106">Adding Connection Manager to an SSIS Package</span></span>  
 <span data-ttu-id="55017-107">Você pode adicionar um novo Gerenciador de Conexões OData a um pacote SSIS de três maneiras:</span><span class="sxs-lookup"><span data-stu-id="55017-107">You can add a new OData Connection Manager to an SSIS package in three ways:</span></span>  
  
-   <span data-ttu-id="55017-108">Clique no botão **Novo...** em **Editor de origem OData**</span><span class="sxs-lookup"><span data-stu-id="55017-108">Click the **New...** button in the **OData Source Editor**</span></span>  
  
-   <span data-ttu-id="55017-109">Clique com o botão direito na pasta **Gerenciadores de Conexões** no **Gerenciador de Soluções** e clique em **Novo Gerenciador de Conexões**.</span><span class="sxs-lookup"><span data-stu-id="55017-109">Right-click **Connection Managers** folder in the **Solution Explorer** and click **New Connection Manager**.</span></span> <span data-ttu-id="55017-110">Selecione **ODATA** para o **Tipo de gerenciador de conexões**.</span><span class="sxs-lookup"><span data-stu-id="55017-110">Select **ODATA** for **Connection manager type**.</span></span>  
  
-   <span data-ttu-id="55017-111">Clique com o botão direito do mouse no painel **gerenciadores de conexões** na parte inferior do designer de pacotes e selecione **nova conexão...**. Selecione **ODATA** para o **tipo de Gerenciador de conexões**.</span><span class="sxs-lookup"><span data-stu-id="55017-111">Right-click in the **Connection Managers** pane at the bottom of the package designer, and select **New Connection...**. Select **ODATA** for **Connection manager type**.</span></span>  
  
## <a name="connection-manager-authentication"></a><span data-ttu-id="55017-112">Autenticação do gerenciador de conexões</span><span class="sxs-lookup"><span data-stu-id="55017-112">Connection Manager Authentication</span></span>  
 <span data-ttu-id="55017-113">O gerenciador de conexões do OData oferece suporte a dois modos de autenticação.</span><span class="sxs-lookup"><span data-stu-id="55017-113">The OData Connection Manager supports two modes of authentication.</span></span>  
  
-   <span data-ttu-id="55017-114">Autenticação do Windows</span><span class="sxs-lookup"><span data-stu-id="55017-114">Windows Authentication</span></span>  
  
-   <span data-ttu-id="55017-115">Autenticação básica (nome de usuário e senha)</span><span class="sxs-lookup"><span data-stu-id="55017-115">Basic Authentication (username/password)</span></span>  
  
 <span data-ttu-id="55017-116">Para o acesso anônimo, selecione a opção de Autenticação do Windows</span><span class="sxs-lookup"><span data-stu-id="55017-116">For anonymous access, select the Windows Authentication option</span></span>  
  
### <a name="specifying-and-securing-credentials"></a><span data-ttu-id="55017-117">Especificando e protegendo credenciais</span><span class="sxs-lookup"><span data-stu-id="55017-117">Specifying and Securing Credentials</span></span>  
 <span data-ttu-id="55017-118">Se seu serviço OData exigir autenticação básica, você pode especificar um nome de usuário e uma senha no [OData Connection Manager Editor](../odata-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="55017-118">If your OData service requires basic authentication, you can specify a username and password in the [OData Connection Manager Editor](../odata-connection-manager-editor.md).</span></span> <span data-ttu-id="55017-119">Os valores que você insere no publicador são persistidos no pacote.</span><span class="sxs-lookup"><span data-stu-id="55017-119">The values you enter in the editor are persisted in the package.</span></span> <span data-ttu-id="55017-120">O valor de senha é criptografado de acordo com o nível de proteção do pacote.</span><span class="sxs-lookup"><span data-stu-id="55017-120">The password value is encrypted according to the package protection level.</span></span>  
  
 <span data-ttu-id="55017-121">Há várias maneiras de exteriorizar/parametrizar os valores de nome de usuário e senha.</span><span class="sxs-lookup"><span data-stu-id="55017-121">There are multiple ways to externalize/parameterize the username and password values.</span></span> <span data-ttu-id="55017-122">As duas principais maneiras de fazer isso no [!INCLUDE[ssISversion11](../../includes/ssisversion11-md.md)] são usando parâmetros, ou definindo as propriedades do gerenciador de conexões diretamente quando você executa o pacote usando o SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="55017-122">The two primary ways of doing this in [!INCLUDE[ssISversion11](../../includes/ssisversion11-md.md)] are by using parameters, or by setting the connection manager properties directly when you run the package using SQL Server Management Studio.</span></span>  
  
## <a name="odata-connection-manager-properties"></a><span data-ttu-id="55017-123">Propriedades do gerenciador de conexões do OData</span><span class="sxs-lookup"><span data-stu-id="55017-123">OData Connection Manager Properties</span></span>  
 <span data-ttu-id="55017-124">A lista a seguir descreve algumas das propriedades do gerenciador de conexões do OData que talvez você queira alterar.</span><span class="sxs-lookup"><span data-stu-id="55017-124">The following list describes some of the OData Connection Manager properties that you may want to change.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="55017-125">Propriedade</span><span class="sxs-lookup"><span data-stu-id="55017-125">Property</span></span>|<span data-ttu-id="55017-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="55017-126">Description</span></span>|  
|<span data-ttu-id="55017-127">Url</span><span class="sxs-lookup"><span data-stu-id="55017-127">Url</span></span>|<span data-ttu-id="55017-128">URL do documento de serviço.</span><span class="sxs-lookup"><span data-stu-id="55017-128">URL to the service document.</span></span>|  
|<span data-ttu-id="55017-129">UserName</span><span class="sxs-lookup"><span data-stu-id="55017-129">UserName</span></span>|<span data-ttu-id="55017-130">Nome de usuário para ser usado na autenticação básica.</span><span class="sxs-lookup"><span data-stu-id="55017-130">Username to use for Basic Authentication.</span></span>|  
|<span data-ttu-id="55017-131">Senha</span><span class="sxs-lookup"><span data-stu-id="55017-131">Password</span></span>|<span data-ttu-id="55017-132">Senha a ser usada na autenticação básica.</span><span class="sxs-lookup"><span data-stu-id="55017-132">Password to use for Basic Authentication.</span></span>|  
|<span data-ttu-id="55017-133">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="55017-133">ConnectionString</span></span>|<span data-ttu-id="55017-134">Reflete outras propriedades do gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="55017-134">Reflects other properties of the connection manager.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="55017-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="55017-135">See Also</span></span>  
 [<span data-ttu-id="55017-136">Editor de Gerenciador de Conexões OData</span><span class="sxs-lookup"><span data-stu-id="55017-136">OData Connection Manager Editor</span></span>](../odata-connection-manager-editor.md)  
  
  
