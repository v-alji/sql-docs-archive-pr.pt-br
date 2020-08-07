---
title: Criando agregações (Analysis Services-multidimensional) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- aggregations [Analysis Services], partitions
- partitions [Analysis Services], aggregations
ms.assetid: 3072b7e0-6961-42ad-a287-16f391f2cec4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 18d8ea1adb645868a11b70966ba3be2ed1764fbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583196"
---
# <a name="designing-aggregations-analysis-services---multidimensional"></a><span data-ttu-id="38b12-102">Projetando agregações (Analysis Services - multidimensional)</span><span class="sxs-lookup"><span data-stu-id="38b12-102">Designing Aggregations (Analysis Services - Multidimensional)</span></span>
  <span data-ttu-id="38b12-103">As agregações são resumos pré-calculados de dados de cubo que ajudam a habilitar o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para fornecer rápidas respostas de consultas.</span><span class="sxs-lookup"><span data-stu-id="38b12-103">Aggregations are precalculated summaries of cube data that help enable [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to provide rapid query responses.</span></span>  
  
 <span data-ttu-id="38b12-104">Para definir opções de armazenamento e projetar agregações para uma partição, use o Assistente de Design de Agregação.</span><span class="sxs-lookup"><span data-stu-id="38b12-104">To set storage options and design aggregations for a partition, use the Aggregation Design Wizard.</span></span> <span data-ttu-id="38b12-105">O assistente opera em uma única partição de um grupo de medidas por vez, de modo que é possível selecionar opções e projetos diferentes para cada partição.</span><span class="sxs-lookup"><span data-stu-id="38b12-105">The wizard operates on a single partition of a measure group at a time so that you can select different options and designs for each partition.</span></span> <span data-ttu-id="38b12-106">O assistente possui etapas que permitem configurar o armazenamento e projetar agregações para uma partição.</span><span class="sxs-lookup"><span data-stu-id="38b12-106">The wizard takes you through steps to configure storage and design aggregation for a partition.</span></span> <span data-ttu-id="38b12-107">Para obter mais informações sobre como configurar o armazenamento, consulte.</span><span class="sxs-lookup"><span data-stu-id="38b12-107">For more information about configuring storage, see.</span></span>  
  
 <span data-ttu-id="38b12-108">Selecione um método para controlar o número de agregações a serem projetadas e deixe o assistente projetá-las.</span><span class="sxs-lookup"><span data-stu-id="38b12-108">Select a method for controlling the number of aggregations the wizard will design, and then let the wizard design the aggregations.</span></span>  
  
 <span data-ttu-id="38b12-109">O objetivo é projetar o número ideal de agregações.</span><span class="sxs-lookup"><span data-stu-id="38b12-109">The goal is to design the optimal number of aggregations.</span></span> <span data-ttu-id="38b12-110">Esse número não só deve fornecer um tempo de resposta satisfatório, mas também deve impedir o aumento excessivo do tamanho da partição.</span><span class="sxs-lookup"><span data-stu-id="38b12-110">This number should not only provide satisfactory response time, but also prevent excessive partition size.</span></span> <span data-ttu-id="38b12-111">Um número maior de agregações produz tempos de resposta mais rápidos, mas também requer mais espaço de armazenamento e pode demorar mais para ser calculado.</span><span class="sxs-lookup"><span data-stu-id="38b12-111">A greater number of aggregations produces faster response times but it also requires more storage space and may take longer to compute.</span></span> <span data-ttu-id="38b12-112">Além disso, como o assistente projeta cada vez mais agregações, as agregações mais antigas têm um ganho de desempenho consideravelmente maior do que as agregações mais recentes.</span><span class="sxs-lookup"><span data-stu-id="38b12-112">Moreover, as the wizard designs more and more aggregations, earlier aggregations produce considerably larger performance gains than later aggregations.</span></span> <span data-ttu-id="38b12-113">A redução nas agregações menos úteis também aumenta o desempenho.</span><span class="sxs-lookup"><span data-stu-id="38b12-113">Reduction in less useful aggregations increases performance as well.</span></span> <span data-ttu-id="38b12-114">É possível controlar o número de agregações projetadas pelo assistente com um dos seguintes métodos disponíveis:</span><span class="sxs-lookup"><span data-stu-id="38b12-114">You can control the number of aggregations the wizard designs by one of the following methods available in the wizard:</span></span>  
  
-   <span data-ttu-id="38b12-115">Especifique um limite de espaço de armazenamento para as agregações.</span><span class="sxs-lookup"><span data-stu-id="38b12-115">Specify a storage space limit for the aggregations.</span></span>  
  
-   <span data-ttu-id="38b12-116">Especifique um limite de ganho de desempenho.</span><span class="sxs-lookup"><span data-stu-id="38b12-116">Specify a performance gain limit.</span></span>  
  
-   <span data-ttu-id="38b12-117">Pare o assistente manualmente quando a curva de desempenho versus tamanho exibida começar a ficar nivelada em um ganho de desempenho aceitável.</span><span class="sxs-lookup"><span data-stu-id="38b12-117">Stop the wizard manually when the displayed performance versus size curve starts to level off at an acceptable performance gain.</span></span>  
  
-   <span data-ttu-id="38b12-118">Opte por não projetar agregações.</span><span class="sxs-lookup"><span data-stu-id="38b12-118">Choose not to design aggregations.</span></span>  
  
 <span data-ttu-id="38b12-119">Para projetar o armazenamento, o assistente deve se conectar ao [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="38b12-119">To design storage, the wizard must be able to connect to [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] on the target server.</span></span> <span data-ttu-id="38b12-120">O assistente exibirá uma mensagem de erro se o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] não estiver em execução no servidor de destino ou se o processo de projeto do armazenamento não conseguir se conectar ao servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="38b12-120">The wizard will display an error message if [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] is not running on the target server or if the storage design process is otherwise unable to connect to the target server.</span></span>  
  
 <span data-ttu-id="38b12-121">A etapa final do assistente permite processar ou adiar o processamento.</span><span class="sxs-lookup"><span data-stu-id="38b12-121">The final step of the wizard allows you to process or defer processing.</span></span> <span data-ttu-id="38b12-122">O processamento cria as agregações projetadas com o assistente, enquanto o adiamento salva as agregações projetadas para serem processadas posteriormente, permitindo a continuidade das atividades do projeto sem nenhum processamento.</span><span class="sxs-lookup"><span data-stu-id="38b12-122">Processing creates the aggregations you design with the wizard, while deferring processing saves the designed aggregations for future processing, thus allowing design activities to continue without processing.</span></span> <span data-ttu-id="38b12-123">Dependendo do tamanho da partição, o processamento pode demorar algum tempo.</span><span class="sxs-lookup"><span data-stu-id="38b12-123">Depending on the size of the partition, processing may take considerable time.</span></span> <span data-ttu-id="38b12-124">Se desejar, você pode interromper o processamento de uma partição.</span><span class="sxs-lookup"><span data-stu-id="38b12-124">If you choose, you can interrupt processing a partition.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38b12-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="38b12-125">See Also</span></span>  
 [<span data-ttu-id="38b12-126">Agregações e designs de agregação</span><span class="sxs-lookup"><span data-stu-id="38b12-126">Aggregations and Aggregation Designs</span></span>](../multidimensional-models-olap-logical-cube-objects/aggregations-and-aggregation-designs.md)  
  
  
