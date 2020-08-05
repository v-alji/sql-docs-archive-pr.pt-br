---
title: Selecionar a dimensão do cubo de origem (Assistente de mineração de dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.dmwizard.selectsourcecube.f1
ms.assetid: 556e216b-5e21-4160-967d-4c57591fbab4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6295a5312b4501236e0ce8f5776fc43c0d014581
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570891"
---
# <a name="select-the-source-cube-dimension-data-mining-wizard"></a><span data-ttu-id="8d998-102">Selecionar a dimensão do cubo de origem (Assistente de Mineração de Dados)</span><span class="sxs-lookup"><span data-stu-id="8d998-102">Select the Source Cube Dimension (Data Mining Wizard)</span></span>
  <span data-ttu-id="8d998-103">Use a página **Selecionar a Dimensão do Cubo de Origem** para selecionar a dimensão do cubo que contém os casos a serem analisados.</span><span class="sxs-lookup"><span data-stu-id="8d998-103">Use the **Select the Source Cube Dimension** page to select the dimension from the cube that contains the cases you want to analyze.</span></span> <span data-ttu-id="8d998-104">Por exemplo, se você estiver criando um modelo que analise o comportamento de compra dos clientes com base em dados demográficos, selecione a dimensão Cliente, que em geral contém um registro exclusivo para cada cliente e vários atributos que representam dados demográficos, como sexo, local ou renda.</span><span class="sxs-lookup"><span data-stu-id="8d998-104">For example, if you are building a model that analyzes the purchasing behavior of customers based on demographics, you would select the Customer dimension, which typically contains a unique record for each customer and various attributes that represent demographics, such as gender, location, or income.</span></span> <span data-ttu-id="8d998-105">Posteriormente no assistente, você terá a oportunidade de adicionar uma tabela relacionada a essa tabela de casos: por exemplo, você pode adicionar uma tabela aninhada que mostre quais produtos o cliente comprou.</span><span class="sxs-lookup"><span data-stu-id="8d998-105">Later in the wizard you will have the opportunity to add a table that is related to this case table: for example, you might add a nested table that shows which products the customer has purchased.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8d998-106">Essa página será exibida apenas se você tiver selecionado **De cubo existente** na página **Selecionar o Método de Definição** do assistente.</span><span class="sxs-lookup"><span data-stu-id="8d998-106">This page will appear only if you have selected **From existing cube** on the **Select the Definition Method** page of the wizard.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8d998-107">Opções</span><span class="sxs-lookup"><span data-stu-id="8d998-107">Options</span></span>  
 <span data-ttu-id="8d998-108">**Selecionar a Dimensão do Cubo de Origem**</span><span class="sxs-lookup"><span data-stu-id="8d998-108">**Select a Source Cube Dimension**</span></span>  
 <span data-ttu-id="8d998-109">Selecione a dimensão do cubo que fornecerá os dados de origem para sua estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="8d998-109">Select the dimension of the cube that will provide the source data for your mining structure.</span></span>  
  
## <a name="choosing-a-dimension"></a><span data-ttu-id="8d998-110">Escolhendo uma dimensão</span><span class="sxs-lookup"><span data-stu-id="8d998-110">Choosing a Dimension</span></span>  
 <span data-ttu-id="8d998-111">Como você pode selecionar apenas uma dimensão para uso no modelo, é importante entender a estrutura do cubo e selecionar a dimensão que fornece as melhores informações para o modelo.</span><span class="sxs-lookup"><span data-stu-id="8d998-111">Because you can select only one dimension for use in your model, it is important that you understand the cube structure and select the dimension that provides the best information for your model.</span></span> <span data-ttu-id="8d998-112">Se você não tiver certeza em relação a qual dimensão usar, talvez seja útil percorrer o cubo e examinar os campos e os dados nele usando o Designer de Dimensão.</span><span class="sxs-lookup"><span data-stu-id="8d998-112">If you are not sure which dimension to use, it might be helpful to browse the cube and review the fields and the data in them by using Dimension Designer.</span></span> <span data-ttu-id="8d998-113">Para obter mais informações, consulte [Procurar dados de dimensão no Designer de Dimensão](multidimensional-models/database-dimensions-browse-dimension-data-in-dimension-designer.md).</span><span class="sxs-lookup"><span data-stu-id="8d998-113">For more information, see [Browse Dimension Data in Dimension Designer](multidimensional-models/database-dimensions-browse-dimension-data-in-dimension-designer.md).</span></span>  
  
 <span data-ttu-id="8d998-114">Se não estiver familiarizado com as dimensões em geral, consulte [Introdução a Dimensões &#40;Analysis Services – Dados Multidimensionais&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="8d998-114">If you are unfamiliar with dimensions in general, see [Introduction to Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="8d998-115">Para saber mais sobre o tipo de informações geralmente contidas em uma única dimensão, incluindo os atributos e as medidas que podem ser úteis para mineração de dados, consulte [Relações de dimensão](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="8d998-115">For more information about the type of information that is typically contained in a single dimension, including attributes and measures that might be useful for data mining, see [Dimension Relationships](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md).</span></span>  
  
 <span data-ttu-id="8d998-116">Se a dimensão escolhida não contiver todos os atributos relacionados necessários para criar o modelo de mineração de dados, talvez seja necessário modificá-la.</span><span class="sxs-lookup"><span data-stu-id="8d998-116">If the dimension that you choose does not contain all of the related attributes that you need to build the data mining model, you might need to modify the dimension.</span></span> <span data-ttu-id="8d998-117">Para obter mais informações, consulte [Definir as dimensões do banco de dados](multidimensional-models/define-database-dimensions.md).</span><span class="sxs-lookup"><span data-stu-id="8d998-117">For more information, see [Define Database Dimensions](multidimensional-models/define-database-dimensions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d998-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8d998-118">See Also</span></span>  
 <span data-ttu-id="8d998-119">[Ajuda F1 do assistente de mineração de dados &#40;Analysis Services Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="8d998-119">[Data Mining Wizard F1 Help &#40;Analysis Services - Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="8d998-120">[Criar a estrutura de mineração de dados &#40;assistente de mineração de dados&#41;](create-the-data-mining-structure-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="8d998-120">[Create the Data Mining Structure &#40;Data Mining Wizard&#41;](create-the-data-mining-structure-data-mining-wizard.md) </span></span>  
 [<span data-ttu-id="8d998-121">Selecione a chave de caso &#40;assistente de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="8d998-121">Select the Case Key &#40;Data Mining Wizard&#41;</span></span>](select-the-case-key-data-mining-wizard.md)  
  
  
