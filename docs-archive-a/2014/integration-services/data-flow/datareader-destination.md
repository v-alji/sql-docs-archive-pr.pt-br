---
title: Destino do DataReader | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.datareaderdest.f1
helpviewer_keywords:
- DataReader destination
- destinations [Integration Services], DataReader
ms.assetid: 56fcc4bf-c901-42c3-a71d-110039293431
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 40cfe5d99c33eb19d415f204173005a64bde7855
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685877"
---
# <a name="datareader-destination"></a><span data-ttu-id="fc25a-102">Destino DataReader</span><span class="sxs-lookup"><span data-stu-id="fc25a-102">DataReader Destination</span></span>
  <span data-ttu-id="fc25a-103">O destino do DataReader expõe os dados em um fluxo de dados com o uso da interface `DataReader` do ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="fc25a-103">The DataReader destination exposes the data in a data flow by using the ADO.NET `DataReader` interface.</span></span> <span data-ttu-id="fc25a-104">Os dados podem ser consumidos por outros aplicativos.</span><span class="sxs-lookup"><span data-stu-id="fc25a-104">The data can then be consumed by other applications.</span></span> <span data-ttu-id="fc25a-105">Por exemplo, você pode configurar a fonte de dados de um relatório do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] para usar o resultado de execução de um pacote do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fc25a-105">For example, you can configure the data source of a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report to use the result of running a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package.</span></span> <span data-ttu-id="fc25a-106">Para fazer isso, crie um fluxo de dados que implementa o destino do DataReader.</span><span class="sxs-lookup"><span data-stu-id="fc25a-106">To do this, you create a data flow that implements the DataReader destination.</span></span>  
  
 <span data-ttu-id="fc25a-107">Para obter informações sobre como acessar e ler valores no destino do DataReader programaticamente, consulte [Carregando a saída de um pacote local](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md).</span><span class="sxs-lookup"><span data-stu-id="fc25a-107">For information about accessing and reading values in the DataReader destination programmatically, see [Loading the Output of a Local Package](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md).</span></span>  
  
## <a name="configuration-of-the-datareader-destination"></a><span data-ttu-id="fc25a-108">Configuração do destino do DataReader</span><span class="sxs-lookup"><span data-stu-id="fc25a-108">Configuration of the DataReader Destination</span></span>  
 <span data-ttu-id="fc25a-109">Você pode especificar um valor de tempo limite para o destino do DataReader e indicar se o destino deveria falhar se ocorresse um tempo limite.</span><span class="sxs-lookup"><span data-stu-id="fc25a-109">You can specify a time-out value for the DataReader destination and indicate whether the destination should fail if a time-out occurs.</span></span> <span data-ttu-id="fc25a-110">Um tempo limite ocorre se o aplicativo não fizer uma solicitação de dados no tempo especificado.</span><span class="sxs-lookup"><span data-stu-id="fc25a-110">A time-out occurs if the application does not ask for data within the specified time.</span></span>  
  
 <span data-ttu-id="fc25a-111">O destino do DataReader tem uma entrada.</span><span class="sxs-lookup"><span data-stu-id="fc25a-111">The DataReader destination has one input.</span></span> <span data-ttu-id="fc25a-112">Não dá suporte a uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="fc25a-112">It does not support an error output.</span></span>  
  
 <span data-ttu-id="fc25a-113">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="fc25a-113">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="fc25a-114">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor Avançado** ou programaticamente, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="fc25a-114">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="fc25a-115">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="fc25a-115">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="fc25a-116">Propriedades personalizadas do destino DataReader</span><span class="sxs-lookup"><span data-stu-id="fc25a-116">DataReader Destination Custom Properties</span></span>](datareader-destination-custom-properties.md)  
  
 <span data-ttu-id="fc25a-117">Para obter mais informações sobre como definir as propriedades, consulte [Definir as propriedades de um componente de fluxo de dados](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="fc25a-117">For more information about how to set properties, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
