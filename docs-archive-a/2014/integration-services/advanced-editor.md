---
title: Editor Avançado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.advancededitor.columnmappings.f1
- sql12.dts.designer.advancededitor.inputcolumns.f1
- sql12.dts.designer.advancededitor.columnproperties.f1
- sql12.dts.designer.advancededitor.componentproperties.f1
- sql12.dts.designer.advancededitor.connections.f1
ms.assetid: 5ad0ac71-fa8b-4c26-bd42-e6ef00c87571
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7f4897f2589acdeb93efecbdf9aacde07d21ca42
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571537"
---
# <a name="advanced-editor"></a><span data-ttu-id="32cf0-102">Editor Avançado</span><span class="sxs-lookup"><span data-stu-id="32cf0-102">Advanced Editor</span></span>
  <span data-ttu-id="32cf0-103">Use a caixa de diálogo **Editor Avançado** para configurar propriedades para o objeto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] selecionado.</span><span class="sxs-lookup"><span data-stu-id="32cf0-103">Use the **Advanced Editor** dialog box to configure to configure properties for the selected [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] object.</span></span>  
  
 <span data-ttu-id="32cf0-104">O **Editor Avançado** está disponível para a maioria dos objetos [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que têm propriedades configuráveis.</span><span class="sxs-lookup"><span data-stu-id="32cf0-104">The **Advanced Editor** is available for most [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] objects that have configurable properties.</span></span> <span data-ttu-id="32cf0-105">É o único editor disponível para os objetos que não expõem uma interface de usuário personalizada.</span><span class="sxs-lookup"><span data-stu-id="32cf0-105">It is the only editor available for those objects that do not expose a custom user interface.</span></span>  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="32cf0-106">têm propriedades que podem ser definidas no nível de componente, no nível de entrada e saída e no nível de coluna de entrada e saída.</span><span class="sxs-lookup"><span data-stu-id="32cf0-106">data flow objects have properties that can be set at the component level, the input and output level, and the input and output column level.</span></span> <span data-ttu-id="32cf0-107">O **Editor Avançado** enumera todas as propriedades comuns e personalizadas do objeto selecionado, e as exibe em até quatro das cinco guias a seguir, conforme aplicável:</span><span class="sxs-lookup"><span data-stu-id="32cf0-107">The **Advanced Editor** enumerates all the common and custom properties of the selected object and displays them on up to four of the following five tabs as applicable:</span></span>  
  
-   <span data-ttu-id="32cf0-108">**Gerenciadores de Conexões** – use esta guia para definir propriedades de conexão</span><span class="sxs-lookup"><span data-stu-id="32cf0-108">**Connection Managers** -- use this tab to set connection properties</span></span>  
  
-   <span data-ttu-id="32cf0-109">**Propriedades do Componente** – use esta guia para definir propriedades no nível do componente</span><span class="sxs-lookup"><span data-stu-id="32cf0-109">**Component Properties** -- use this tab to set component-level properties</span></span>  
  
-   <span data-ttu-id="32cf0-110">**Mapeamentos de Colunas** – use esta guia para mapear as colunas disponíveis como colunas de saída</span><span class="sxs-lookup"><span data-stu-id="32cf0-110">**Column Mappings** -- use this tab to map available columns as output columns</span></span>  
  
-   <span data-ttu-id="32cf0-111">**Colunas de Entrada** – use esta guia para selecionar colunas de entrada</span><span class="sxs-lookup"><span data-stu-id="32cf0-111">**Input Columns** -- use this tab to select input columns</span></span>  
  
-   <span data-ttu-id="32cf0-112">**Propriedades de Entrada e Saída** – use essa guia para definir as propriedades de entrada e saída e para adicionar e remover saídas, selecionar ou remover colunas para entradas e saídas e definir propriedades para entradas e saídas</span><span class="sxs-lookup"><span data-stu-id="32cf0-112">**Input and Output Properties** -- use this tab to set input and output properties; and to add and remove outputs, select or remove columns for inputs and outputs, and set properties for inputs and outputs</span></span>  
  
 <span data-ttu-id="32cf0-113">As propriedades exibidas variam por componente.</span><span class="sxs-lookup"><span data-stu-id="32cf0-113">The properties displayed vary by component.</span></span> <span data-ttu-id="32cf0-114">Para obter mais informações sobre as propriedades que podem ser exibidas no **Editor Avançado**, consulte os tópicos a seguir:</span><span class="sxs-lookup"><span data-stu-id="32cf0-114">For more information on the properties that may be displayed in the **Advanced Editor**, see the following topics:</span></span>  
  
-   [<span data-ttu-id="32cf0-115">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="32cf0-115">Common Properties</span></span>](../../2014/integration-services/common-properties.md)  
  
-   [<span data-ttu-id="32cf0-116">Propriedades personalizadas de Transformação</span><span class="sxs-lookup"><span data-stu-id="32cf0-116">Transformation Custom Properties</span></span>](data-flow/transformations/transformation-custom-properties.md)  
  
-   [<span data-ttu-id="32cf0-117">Propriedades do caminho</span><span class="sxs-lookup"><span data-stu-id="32cf0-117">Path Properties</span></span>](../../2014/integration-services/path-properties.md)  
  
 <span data-ttu-id="32cf0-118">Para obter mais informações sobre o componente específico que você está editando, consulte a descrição do componente na seção Data Flow Elements da documentação [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Objects and Concepts:</span><span class="sxs-lookup"><span data-stu-id="32cf0-118">For more information about the specific component that you are editing, see the description of the component in the Data Flow Elements section of the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Objects and Concepts documentation:</span></span>  
  
-   [<span data-ttu-id="32cf0-119">Transformações do Integration Services</span><span class="sxs-lookup"><span data-stu-id="32cf0-119">Integration Services Transformations</span></span>](data-flow/transformations/integration-services-transformations.md)  
  
## <a name="see-also"></a><span data-ttu-id="32cf0-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="32cf0-120">See Also</span></span>  
 [<span data-ttu-id="32cf0-121">Referência de mensagens e erros do Integration Services</span><span class="sxs-lookup"><span data-stu-id="32cf0-121">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
