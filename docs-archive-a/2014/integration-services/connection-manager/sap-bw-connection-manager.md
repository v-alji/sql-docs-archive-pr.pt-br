---
title: Gerenciador de Conexões de SAP BW | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 06b166a1-a9df-48ea-a0e8-9b8d6979c0a1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bc3bb32c4895c6ec8fbcf31d57e8685c74de32dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570815"
---
# <a name="sap-bw-connection-manager"></a><span data-ttu-id="a9b37-102">Gerenciador de Conexões SAP BW</span><span class="sxs-lookup"><span data-stu-id="a9b37-102">SAP BW Connection Manager</span></span>
  <span data-ttu-id="a9b37-103">O gerenciador de conexões SAP BW é o componente de gerenciador de conexões do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 para SAP BW.</span><span class="sxs-lookup"><span data-stu-id="a9b37-103">The SAP BW connection manager is the connection manager component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span> <span data-ttu-id="a9b37-104">Portanto, o gerenciador de conexões do SAP BW fornece a conectividade para um sistema SAP Netweaver BW versão 7 que os componentes de origem e destino do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 para SAP BW precisam.</span><span class="sxs-lookup"><span data-stu-id="a9b37-104">Thus, the SAP BW connection manager provides the connectivity to an SAP Netweaver BW version 7 system that the source and destination components of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW need.</span></span> <span data-ttu-id="a9b37-105">(A origem e o destino SAP BW que fazem parte do pacote do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 para SAP BW são os únicos componentes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que usam o gerenciador de conexões do SAP BW.)</span><span class="sxs-lookup"><span data-stu-id="a9b37-105">(The SAP BW source and destination that are part of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW package are the only [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] components that use the SAP BW connection manager.)</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a9b37-106">A documentação do Microsoft Connector 1.1 for SAP BW supõe familiaridade com o ambiente do SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="a9b37-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="a9b37-107">Para obter mais informações sobre o SAP Netweaver BW ou para obter informações sobre como configurar objetos e processos do SAP Netweaver BW, consulte sua documentação do SAP.</span><span class="sxs-lookup"><span data-stu-id="a9b37-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="a9b37-108">Quando você adiciona um gerenciador de conexões do SAP BW a um pacote, a propriedade `ConnectionManagerType` do gerenciador de conexões é definida como `SAPBI`.</span><span class="sxs-lookup"><span data-stu-id="a9b37-108">When you add an SAP BW connection manager to a package, the `ConnectionManagerType` property of the connection manager is set to `SAPBI`.</span></span>  
  
## <a name="configuring-the-sap-bw-connection-manager"></a><span data-ttu-id="a9b37-109">Configurando o gerenciador de conexões SAP BW</span><span class="sxs-lookup"><span data-stu-id="a9b37-109">Configuring the SAP BW Connection Manager</span></span>  
 <span data-ttu-id="a9b37-110">Você pode configurar um gerenciador de conexões SAP BW de uma das seguintes formas:</span><span class="sxs-lookup"><span data-stu-id="a9b37-110">You can configure the SAP BW connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="a9b37-111">Forneça o cliente, o nome de usuário, a senha e o idioma para a conexão.</span><span class="sxs-lookup"><span data-stu-id="a9b37-111">Provide the client, user name, password, and language for the connection.</span></span>  
  
-   <span data-ttu-id="a9b37-112">Escolha se deseja se conectar a um único servidor de aplicativos ou um grupo de servidores com balanceamento de carga.</span><span class="sxs-lookup"><span data-stu-id="a9b37-112">Choose whether to connect to a single application server or to a group of load-balanced servers.</span></span>  
  
-   <span data-ttu-id="a9b37-113">Forneça o host e o número do sistema para um único servidor de aplicativos ou forneça o servidor de mensagens, o grupo e o SID para um grupo de servidores com balanceamento de carga.</span><span class="sxs-lookup"><span data-stu-id="a9b37-113">Provide the host and system number for a single application server, or provide the message server, group, and SID for a group of load-balanced servers.</span></span>  
  
-   <span data-ttu-id="a9b37-114">Habilite o log personalizado das chamadas de função de RFC para os componentes do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 para SAP BW.</span><span class="sxs-lookup"><span data-stu-id="a9b37-114">Enable custom logging of RFC function calls for the components of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span> <span data-ttu-id="a9b37-115">(Esse log é separado do log opcional que você pode habilitar em pacotes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .) Para habilitar o log das chamadas de função de RFC, você especifica um diretório no qual armazenar os arquivos de log que são criados antes e depois de cada chamada de função de RFC.</span><span class="sxs-lookup"><span data-stu-id="a9b37-115">(This logging is separate from the optional logging that you can enable on [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.) To enable logging of RFC function calls, you specify a directory in which to store the log files that are created before and after each RFC function call.</span></span> <span data-ttu-id="a9b37-116">(Esse recurso de registro cria muitos arquivos de log em formato XML.</span><span class="sxs-lookup"><span data-stu-id="a9b37-116">(This logging feature creates many log files in XML format.</span></span> <span data-ttu-id="a9b37-117">Como esses arquivos de log também contêm todas as linhas de dados que são transferidas, esses arquivos de log podem consumir uma grande quantidade de espaço em disco.) Se você não selecionar um diretório de log, o registro em log não será habilitado.</span><span class="sxs-lookup"><span data-stu-id="a9b37-117">As these log files also contain all the rows of data that are transferred, these log files may consume a large amount of disk space.) If you do not select a log directory, logging is not enabled.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="a9b37-118">Se os dados que são transferidos contêm informações confidenciais, os arquivos de log também conterão essas informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="a9b37-118">If the data that is transferred contains sensitive information, the log files will also contain that sensitive information.</span></span>  
  
-   <span data-ttu-id="a9b37-119">Use os valores que você inseriu para testar a conexão.</span><span class="sxs-lookup"><span data-stu-id="a9b37-119">Use the values that you have entered to test the connection.</span></span>  
  
 <span data-ttu-id="a9b37-120">Se você não souber todos os valores necessários para configurar o gerenciador de conexões, talvez precise perguntar ao administrador do SAP.</span><span class="sxs-lookup"><span data-stu-id="a9b37-120">If you do not know all the values that are required to configure the connection manager, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="a9b37-121">Para obter um passo a passo que demonstre como configurar e usar o gerenciador de conexões do SAP BW, a origem e o destino, consulte o white paper [Usando o SQL Server 2008 Integration Services com SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkID=137090).</span><span class="sxs-lookup"><span data-stu-id="a9b37-121">For a walkthrough that demonstrates how to configure and use the SAP BW connection manager, source, and destination, see the white paper, [Using SQL Server 2008 Integration Services with SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkID=137090).</span></span> <span data-ttu-id="a9b37-122">Este white paper também mostra como configurar os objetos necessários no SAP BW.</span><span class="sxs-lookup"><span data-stu-id="a9b37-122">This white paper also shows how to configure the required objects in SAP BW.</span></span>  
  
### <a name="using-the-ssis-designer-to-configure-the-source"></a><span data-ttu-id="a9b37-123">Usando o Designer SSIS para configurar a origem</span><span class="sxs-lookup"><span data-stu-id="a9b37-123">Using the SSIS Designer to Configure the Source</span></span>  
 <span data-ttu-id="a9b37-124">Para obter mais informações sobre as propriedades do gerenciador de conexões do SAP BW que podem ser definidas no [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, clique no tópico a seguir:</span><span class="sxs-lookup"><span data-stu-id="a9b37-124">For more information about the properties of the SAP BW connection manager that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="a9b37-125">Editor do Gerenciador de Conexões de SAP BW</span><span class="sxs-lookup"><span data-stu-id="a9b37-125">SAP BW Connection Manager Editor</span></span>](../sap-bw-connection-manager-editor.md)  
  
## <a name="see-also"></a><span data-ttu-id="a9b37-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a9b37-126">See Also</span></span>  
 [<span data-ttu-id="a9b37-127">Componentes do Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="a9b37-127">Microsoft Connector 1.1 for SAP BW Components</span></span>](../microsoft-connector-for-sap-bw-components.md)  
  
  
