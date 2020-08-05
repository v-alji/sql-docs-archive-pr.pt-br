---
title: Gerenciador de conexões do Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], Analysis Services
- connection managers [Integration Services], Analysis Services
- Analysis Services connection manager
ms.assetid: 9f9cadad-a1d0-4db5-98f5-df5dbbec1be4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b5da84acd131b75ef9ea174986836265934fb44b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574233"
---
# <a name="analysis-services-connection-manager"></a><span data-ttu-id="9c430-102">Gerenciador de conexões do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="9c430-102">Analysis Services Connection Manager</span></span>
  <span data-ttu-id="9c430-103">Um gerenciador de conexões do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] habilita um pacote para se conectar a um servidor que executa um banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ou a um projeto do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que fornece acesso a dados de cubos e dimensões.</span><span class="sxs-lookup"><span data-stu-id="9c430-103">An [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager enables a package to connect to a server that runs an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database or to an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project that provides access to cube and dimension data.</span></span> <span data-ttu-id="9c430-104">Você só pode se conectar a um projeto do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] enquanto estiver desenvolvendo pacotes no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c430-104">You can only connect to an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project while developing packages in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="9c430-105">Em tempo de execução, os pacotes são conectados ao servidor e ao banco de dados em que foi implantado o projeto [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9c430-105">At run time, packages connect to the server and the database to which you deployed the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span>  
  
 <span data-ttu-id="9c430-106">As tarefas Executar DDL do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e Processamento do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e os destinos, como o destino Treinamento do Modelo de Mineração de Dados, usam um gerenciador de conexões do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9c430-106">Both tasks, such as the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Execute DDL task and the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Processing task, and destinations, such as the Data Mining Model Training destination, use an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager.</span></span>  
  
 <span data-ttu-id="9c430-107">Para obter mais informações sobre bancos de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], consulte [Bancos de dados de modelo multidimensional &#40;SSAS&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/multidimensional-model-databases-ssas).</span><span class="sxs-lookup"><span data-stu-id="9c430-107">For more information about [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] databases, see [Multidimensional Model Databases &#40;SSAS&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/multidimensional-model-databases-ssas).</span></span>  
  
## <a name="configuration-of-the-analysis-services-connection-manager"></a><span data-ttu-id="9c430-108">Configuração do Gerenciador de Conexões do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="9c430-108">Configuration of the Analysis Services Connection Manager</span></span>  
 <span data-ttu-id="9c430-109">Quando você adiciona um [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Gerenciador de conexões a um pacote, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] o cria um Gerenciador de conexões que é resolvido como uma [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] conexão em tempo de execução, define as propriedades do Gerenciador de conexões e adiciona o Gerenciador de conexões à `Connections` coleção no pacote.</span><span class="sxs-lookup"><span data-stu-id="9c430-109">When you add an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager to a package, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that is resolved as an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span> <span data-ttu-id="9c430-110">A propriedade `ConnectionManagerType` do gerenciador de conexões é definida como `MSOLAP100`.</span><span class="sxs-lookup"><span data-stu-id="9c430-110">The `ConnectionManagerType` property of the connection manager is set to `MSOLAP100`.</span></span>  
  
 <span data-ttu-id="9c430-111">Você pode configurar um gerenciador de conexões do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="9c430-111">You can configure the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="9c430-112">Forneça uma cadeia de conexão configurada para atender aos requisitos do provedor Microsoft OLE Provider para Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="9c430-112">Provide a connection string configured to meet the requirements of the Microsoft OLE Provider for Analysis Services provider.</span></span>  
  
-   <span data-ttu-id="9c430-113">Especifique uma instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ou o projeto do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que deseja conectar.</span><span class="sxs-lookup"><span data-stu-id="9c430-113">Specify the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] or the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project to connect to.</span></span>  
  
-   <span data-ttu-id="9c430-114">Se estiver se conectando a uma instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], especifique o modo de autenticação.</span><span class="sxs-lookup"><span data-stu-id="9c430-114">If you are connecting to an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], specify the authentication mode.</span></span>  
  
-   <span data-ttu-id="9c430-115">Indique se a conexão criada a partir do gerenciador de conexões será retida em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="9c430-115">Indicate whether the connection that is created from the connection manager is retained at run time.</span></span>  
  
 <span data-ttu-id="9c430-116">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="9c430-116">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="9c430-117">Para obter mais informações sobre as propriedades que podem ser definidas no Designer [!INCLUDE[ssIS](../../includes/ssis-md.md)] , clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="9c430-117">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topic:</span></span>  
  
-   [<span data-ttu-id="9c430-118">Referência de IU da caixa de diálogo Adicionar Gerenciador de Conexões do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="9c430-118">Add Analysis Services Connection Manager Dialog Box UI Reference</span></span>](add-analysis-services-connection-manager-dialog-box-ui-reference.md)  
  
 <span data-ttu-id="9c430-119">Para obter informações sobre como configurar um gerenciador de conexões programaticamente, consulte <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> e [Adicionando conexões programaticamente](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="9c430-119">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
  
