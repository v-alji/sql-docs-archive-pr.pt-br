---
title: Itens de relatório personalizados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- extending Reporting Services
- Reporting Services, extending
- custom report items
ms.assetid: 64dcaf2c-1af5-4937-8ff7-98f1ec3b367e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 86b819cb4d305e537a52a2e7f25cdfa3aefa5f9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685463"
---
# <a name="custom-report-items"></a><span data-ttu-id="1c8f9-102">Itens de Relatório Personalizados</span><span class="sxs-lookup"><span data-stu-id="1c8f9-102">Custom Report Items</span></span>
  <span data-ttu-id="1c8f9-103">O [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] fornece um conjunto de ferramentas avançadas para a criação e publicação de relatórios corporativos, o gerenciamento de segurança e de assinaturas, e a extensão da funcionalidade de relatório por meio de uma API abrangente.</span><span class="sxs-lookup"><span data-stu-id="1c8f9-103">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] provides a rich set of tools for building and publishing enterprise reports, managing security and subscriptions, and extending the reporting functionality through a comprehensive API.</span></span> <span data-ttu-id="1c8f9-104">Os relatórios são definidos por meio de uma linguagem baseada em XML chamada linguagem RDL.</span><span class="sxs-lookup"><span data-stu-id="1c8f9-104">Reports are defined using an XML-based language called Report Definition Language (RDL).</span></span> <span data-ttu-id="1c8f9-105">A RDL oferece um conjunto de instruções que descrevem o layout, as informações de consulta e os tipos de itens para um relatório.</span><span class="sxs-lookup"><span data-stu-id="1c8f9-105">RDL provides a set of instructions that describe layout, query information, and item types for a report.</span></span> <span data-ttu-id="1c8f9-106">É possível estender a RDL escrevendo um item de relatório personalizado.</span><span class="sxs-lookup"><span data-stu-id="1c8f9-106">It is possible to extend RDL by writing a custom report item.</span></span> <span data-ttu-id="1c8f9-107">O item de relatório personalizado consiste em um componente de tempo de execução, chamado pelo processador de relatório em tempo de execução, e em um componente de tempo de design, que permite que o item de relatório personalizado esteja disponível no Designer de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="1c8f9-107">The custom report item consists of a run-time component, which is called by the report processor at run time, and a design-time component, which allows the custom report item to be available in Report Designer.</span></span>  
  
 <span data-ttu-id="1c8f9-108">Para obter uma amostra de um item de relatório personalizado totalmente implementado, consulte [Amostras de produto do SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="1c8f9-108">For a sample of a fully implemented custom report item, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="custom-report-item-scenarios"></a><span data-ttu-id="1c8f9-109">Cenários de item de relatório personalizado</span><span class="sxs-lookup"><span data-stu-id="1c8f9-109">Custom Report Item Scenarios</span></span>  
 <span data-ttu-id="1c8f9-110">Os desenvolvedores que precisam integrar o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] a seus aplicativos podem precisar de funcionalidade que não seja nativamente suportada em RDL.</span><span class="sxs-lookup"><span data-stu-id="1c8f9-110">Developers who need to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into their applications may require functionality that is not natively supported in RDL.</span></span> <span data-ttu-id="1c8f9-111">Isso pode incluir itens como: controles de mapa, listas horizontais, listas colunares e matrizes de tabela dinâmica.</span><span class="sxs-lookup"><span data-stu-id="1c8f9-111">This may include items such as: map controls, horizontal lists, columnar lists, and repivotable matrixes.</span></span> <span data-ttu-id="1c8f9-112">Um item de relatório personalizado de tempo de execução pode ser desenvolvido e pode ser distribuído com um aplicativo para atender a essa necessidade.</span><span class="sxs-lookup"><span data-stu-id="1c8f9-112">A run-time custom report item component can be developed and distributed with an application to fill this need.</span></span>  
  
 <span data-ttu-id="1c8f9-113">Além de fornecer funcionalidade que não tem suporte nativo, alguns desenvolvedores podem desejar estender a funcionalidade existente com versões alternativas de controles já incluídas no [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1c8f9-113">In addition to providing functionality that isn't natively supported, some developers may want to extend existing functionality with alternative versions of controls that are already included with [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="1c8f9-114">Nesse cenário, um desenvolvedor poderia fornecer três componentes: um componente de tempo de execução, um componente de tempo de design e um componente de conversão de item de relatório de tempo de design que converta um item de relatório existente em um item de relatório personalizado sob demanda.</span><span class="sxs-lookup"><span data-stu-id="1c8f9-114">In this scenario, a developer could provide three components: a run-time component, a design-time component, and a design-time report item conversion component that converts an existing report item into a custom report item on demand.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1c8f9-115">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="1c8f9-115">In This Section</span></span>  
 [<span data-ttu-id="1c8f9-116">Arquitetura de item de relatório personalizado</span><span class="sxs-lookup"><span data-stu-id="1c8f9-116">Custom Report Item Architecture</span></span>](custom-report-item-architecture.md)  
 <span data-ttu-id="1c8f9-117">Descreve os componentes que compõem um item de relatório personalizado.</span><span class="sxs-lookup"><span data-stu-id="1c8f9-117">Describes the components that make up a custom report item.</span></span>  
  
 [<span data-ttu-id="1c8f9-118">Requisitos de implementação de item de relatório personalizado</span><span class="sxs-lookup"><span data-stu-id="1c8f9-118">Custom Report Item Implementation Requirements</span></span>](custom-report-item-implementation-requirements.md)  
 <span data-ttu-id="1c8f9-119">Descreve os pré-requisitos para a criação de um item de relatório personalizado.</span><span class="sxs-lookup"><span data-stu-id="1c8f9-119">Describes prerequisites for creating a custom report item.</span></span>  
  
 [<span data-ttu-id="1c8f9-120">Criando um componente de item de relatório personalizado em tempo de execução</span><span class="sxs-lookup"><span data-stu-id="1c8f9-120">Creating a Custom Report Item Run-Time Component</span></span>](creating-a-custom-report-item-run-time-component.md)  
 <span data-ttu-id="1c8f9-121">Descreve como criar um componente de tempo de execução de item de relatório personalizado.</span><span class="sxs-lookup"><span data-stu-id="1c8f9-121">Describes how to create a custom report item run-time component.</span></span>  
  
 [<span data-ttu-id="1c8f9-122">Criando um componente de tempo de design de item de relatório personalizado</span><span class="sxs-lookup"><span data-stu-id="1c8f9-122">Creating a Custom Report Item Design-Time Component</span></span>](creating-a-custom-report-item-design-time-component.md)  
 <span data-ttu-id="1c8f9-123">Descreve como criar um componente de tempo de design de item de relatório personalizado.</span><span class="sxs-lookup"><span data-stu-id="1c8f9-123">Describes how to create a custom report item design-time component.</span></span>  
  
 [<span data-ttu-id="1c8f9-124">Como: implantar um Item de relatório personalizado</span><span class="sxs-lookup"><span data-stu-id="1c8f9-124">How to: Deploy a Custom Report Item</span></span>](how-to-deploy-a-custom-report-item.md)  
 <span data-ttu-id="1c8f9-125">Descreve como implantar um item de relatório personalizado.</span><span class="sxs-lookup"><span data-stu-id="1c8f9-125">Describes how to deploy a custom report item.</span></span>  
  
 [<span data-ttu-id="1c8f9-126">Bibliotecas de classes de itens de relatório personalizados</span><span class="sxs-lookup"><span data-stu-id="1c8f9-126">Custom Report Item Class Libraries</span></span>](custom-report-item-class-libraries.md)  
 <span data-ttu-id="1c8f9-127">Descreve as classes de infraestrutura de item de relatório personalizado e as classes wrapper gerenciadas do namespace `Microsoft.ReportDesigner`.</span><span class="sxs-lookup"><span data-stu-id="1c8f9-127">Describes the custom report item infrastructure classes and managed wrapper classes in the `Microsoft.ReportDesigner` namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c8f9-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1c8f9-128">See Also</span></span>  
 [<span data-ttu-id="1c8f9-129">Referência técnica &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="1c8f9-129">Technical Reference &#40;SSRS&#41;</span></span>](../technical-reference-ssrs.md)  
  
  
