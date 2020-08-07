---
title: Algoritmos de plug-in | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- third-party algorithms [Analysis Services]
- algorithms [data mining], creating
- plugin algorithms [Analysis Services]
ms.assetid: fe364ddc-576e-42fc-9ced-baa399992f92
author: minewiskan
ms.author: owend
ms.openlocfilehash: ebc5e007dcc6de7fb25d59547e21f1e892100570
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681928"
---
# <a name="plugin-algorithms"></a><span data-ttu-id="e1c80-102">Algoritmos de plug-in</span><span class="sxs-lookup"><span data-stu-id="e1c80-102">Plugin Algorithms</span></span>
  <span data-ttu-id="e1c80-103">Além dos algoritmos que o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] fornece, há muitos outros algoritmos que você pode usar para Data Mining.</span><span class="sxs-lookup"><span data-stu-id="e1c80-103">In addition to the algorithms that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] provides, there are many other algorithms that you can use for data mining.</span></span> <span data-ttu-id="e1c80-104">Conforme o caso, o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] fornece um mecanismo de "plugin" para algoritmos que são criados por terceiros.</span><span class="sxs-lookup"><span data-stu-id="e1c80-104">Accordingly, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] provides a mechanism for "plugging in" algorithms that are created by third parties.</span></span> <span data-ttu-id="e1c80-105">Contanto que os algoritmos sigam determinados padrões, é possível usá-los com o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] da mesma forma que os algoritmos da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e1c80-105">As long as the algorithms follow certain standards, you can use them within [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] just as you use the [!INCLUDE[msCoName](../../includes/msconame-md.md)] algorithms.</span></span> <span data-ttu-id="e1c80-106">Os algoritmos de plug-in têm todos os recursos dos algoritmos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] fornecidos pelo.</span><span class="sxs-lookup"><span data-stu-id="e1c80-106">Plugin algorithms have all the capabilities of algorithms that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] provides.</span></span>  
  
 <span data-ttu-id="e1c80-107">Para obter uma descrição completa das interfaces que o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] usa para comunicar-se com algoritmos de plugin, consulte os exemplos para criar um algoritmo personalizado e um visualizador de modelo personalizado que estão publicados no site do [CodePlex](https://go.microsoft.com/fwlink/?LinkID=87843) .</span><span class="sxs-lookup"><span data-stu-id="e1c80-107">For a full description of the interfaces that [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] uses to communicate with plugin algorithms, see the samples for creating a custom algorithm and custom model viewer that are published on [CodePlex](https://go.microsoft.com/fwlink/?LinkID=87843) Web site.</span></span>  
  
## <a name="algorithm-requirements"></a><span data-ttu-id="e1c80-108">Requisitos de algoritmo</span><span class="sxs-lookup"><span data-stu-id="e1c80-108">Algorithm Requirements</span></span>  
 <span data-ttu-id="e1c80-109">Para conectar um algoritmo no [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], é necessário implementar as seguintes interfaces COM:</span><span class="sxs-lookup"><span data-stu-id="e1c80-109">To plug an algorithm into [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], you must implement the following COM interfaces:</span></span>  
  
 `IDMAlgorithm`  
 <span data-ttu-id="e1c80-110">Implementa um algoritmo que produz modelos e implementa as operações de previsão dos modelos resultantes.</span><span class="sxs-lookup"><span data-stu-id="e1c80-110">Implements an algorithm that produces models, and implements the prediction operations of the resulting models.</span></span>  
  
 `IDMAlgorithmNavigation`  
 <span data-ttu-id="e1c80-111">Permite que navegadores acessem o conteúdo dos modelos.</span><span class="sxs-lookup"><span data-stu-id="e1c80-111">Enables browsers to access the content of the models.</span></span>  
  
 `IDMPersist`  
 <span data-ttu-id="e1c80-112">Habilita os modelos que o algoritmo treina para serem salvos e carregados pelo [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e1c80-112">Enables the models that the algorithm trains to be saved and loaded by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
 `IDMAlgorithmMetadata`  
 <span data-ttu-id="e1c80-113">Descreve os recursos e parâmetros de entrada do algoritmo.</span><span class="sxs-lookup"><span data-stu-id="e1c80-113">Describes the capabilities and input parameters of the algorithm.</span></span>  
  
 `IDMAlgorithmFactory`  
 <span data-ttu-id="e1c80-114">Cria instâncias dos objetos que implementam a interface de algoritmo e fornece ao [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] acesso para a interface de metadados de algoritmo.</span><span class="sxs-lookup"><span data-stu-id="e1c80-114">Creates instances of the objects that implement the algorithm interface, and provides [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] with access to the algorithm-metadata interface.</span></span>  
  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="e1c80-115">usa essas interfaces COM para se comunicar com algoritmos de plugin.</span><span class="sxs-lookup"><span data-stu-id="e1c80-115">uses these COM interfaces to communicate with plugin algorithms.</span></span> <span data-ttu-id="e1c80-116">Embora os algoritmos de plugin que você usa devam oferecer suporte à especificação [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB for Data Mining, eles não oferecem suporte a todas as opções de mineração de dados na especificação.</span><span class="sxs-lookup"><span data-stu-id="e1c80-116">Although plugin algorithms that you use must support the [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB for Data Mining specification, they do not have to support all the data mining options in the specification.</span></span> <span data-ttu-id="e1c80-117">Você pode usar o conjunto de linhas do esquema [MINING_SERVICES](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-services-rowset) para determinar os recursos de um algoritmo.</span><span class="sxs-lookup"><span data-stu-id="e1c80-117">You can use the [MINING_SERVICES](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-services-rowset) schema rowset to determine the capabilities of an algorithm.</span></span> <span data-ttu-id="e1c80-118">Esse conjunto de linhas de esquema lista as opções de suporte à mineração de dados para cada provedor de algoritmo de plugin.</span><span class="sxs-lookup"><span data-stu-id="e1c80-118">This schema rowset lists the data mining support options for each plugin algorithm provider.</span></span>  
  
 <span data-ttu-id="e1c80-119">É necessário registrar os novos algoritmos antes de usá-los com o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e1c80-119">You must register new algorithms before you use them with [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="e1c80-120">Para registrar um algoritmo, inclua as seguintes informações no arquivo .ini file da instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] na qual você deseja incluir os algoritmos:</span><span class="sxs-lookup"><span data-stu-id="e1c80-120">To register an algorithm, include the following information in the .ini file of the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] on which you want to include the algorithms:</span></span>  
  
-   <span data-ttu-id="e1c80-121">O nome do algoritmo</span><span class="sxs-lookup"><span data-stu-id="e1c80-121">The algorithm name</span></span>  
  
-   <span data-ttu-id="e1c80-122">PROGID (ele é opcional e será incluído apenas para algoritmos de plugin)</span><span class="sxs-lookup"><span data-stu-id="e1c80-122">ProgID (this is optional and will only be included for plugin algorithms)</span></span>  
  
-   <span data-ttu-id="e1c80-123">Um sinalizador que indique se o algoritmo está habilitado ou não</span><span class="sxs-lookup"><span data-stu-id="e1c80-123">A flag that indicates whether the algorithm is enabled or not</span></span>  
  
 <span data-ttu-id="e1c80-124">O exemplo de código a seguir ilustra como registrar um novo algoritmo:</span><span class="sxs-lookup"><span data-stu-id="e1c80-124">The following code sample illustrates how to register a new algorithm:</span></span>  
  
 `<ConfigurationSettings>`  
  
 `...`  
  
 `<DataMining>`  
  
 `...`  
  
 `<Algorithms>`  
  
 `...`  
  
 `<Sample_Plugin_Algorithm>`  
  
 `<Enabled>1</Enabled>`  
  
 `<ProgID>Microsoft.DataMining.SamplePlugInAlgorithm.Factory</ProgID>`  
  
 `</Sample_PlugIn_Algorithm>`  
  
 `...`  
  
 `</Algorithms>`  
  
 `...`  
  
 `</DataMining>`  
  
 `...`  
  
 `</ConfigurationSettings>`  
  
## <a name="see-also"></a><span data-ttu-id="e1c80-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e1c80-125">See Also</span></span>  
 <span data-ttu-id="e1c80-126">[Algoritmos de mineração de dados &#40;mineração de dados Analysis Services&#41;](data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="e1c80-126">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="e1c80-127">Conjunto de linhas DMSCHEMA_MINING_SERVICES</span><span class="sxs-lookup"><span data-stu-id="e1c80-127">DMSCHEMA_MINING_SERVICES Rowset</span></span>](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-services-rowset)  
  
  
