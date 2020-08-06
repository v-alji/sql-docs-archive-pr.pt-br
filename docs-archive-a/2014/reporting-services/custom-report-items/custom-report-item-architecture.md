---
title: Arquitetura de item de relatório personalizado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom report items, architecture
ms.assetid: 2a88ea46-c9f8-4dd7-aad1-16de11da4f06
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a053eb55547da9030eebe9036667cca2e14606f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569209"
---
# <a name="custom-report-item-architecture"></a><span data-ttu-id="6a680-102">Arquitetura de item de relatório personalizado</span><span class="sxs-lookup"><span data-stu-id="6a680-102">Custom Report Item Architecture</span></span>
  <span data-ttu-id="6a680-103">Um item de relatório personalizado é uma extensão da linguagem RDL que permite que desenvolvedores adicionem funcionalidade que não tem suporte nativo na RDL ou estendam a funcionalidade de controles existentes.</span><span class="sxs-lookup"><span data-stu-id="6a680-103">A custom report item is an extension to the Report Definition Language (RDL) that allows developers to add functionality that's not natively supported in RDL or extend the functionality of existing controls.</span></span> <span data-ttu-id="6a680-104">Existem dois componentes principais para um item de relatório personalizado: o componente de tempo de execução e o componente tempo de design.</span><span class="sxs-lookup"><span data-stu-id="6a680-104">There are two main components to a custom report item: the run-time component and the design-time component.</span></span> <span data-ttu-id="6a680-105">Esses componentes são implementados como assemblies [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] e podem ser escritos em qualquer linguagem em conformidade com CLS.</span><span class="sxs-lookup"><span data-stu-id="6a680-105">These components are implemented as [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] assemblies, and can be written in any CLS-compliant language.</span></span>  
  
## <a name="the-run-time-component"></a><span data-ttu-id="6a680-106">O componente de tempo de execução</span><span class="sxs-lookup"><span data-stu-id="6a680-106">The Run-Time Component</span></span>  
 <span data-ttu-id="6a680-107">O componente de tempo de execução para um item de relatório personalizado é chamado em tempo de execução pelo processador de relatório.</span><span class="sxs-lookup"><span data-stu-id="6a680-107">The run-time component for a custom report item is called by the report processor at run time.</span></span> <span data-ttu-id="6a680-108">O componente de tempo de execução aceita dados passados pelo processador de relatório em tempo de execução, processa seus dados e retorna uma imagem com o item de relatório personalizado renderizado.</span><span class="sxs-lookup"><span data-stu-id="6a680-108">The run-time component accepts data passed by the report processor at run time, processes this data, and returns an image containing the rendered custom report item.</span></span>  
  
 <span data-ttu-id="6a680-109">![Componente em tempo de execução de item de relatório personalizado](../../../2014/reporting-services/media/customreportitemrun-timecomponentarchitecture.gif "Componente em tempo de execução de item de relatório personalizado")</span><span class="sxs-lookup"><span data-stu-id="6a680-109">![Custom report item run-time component](../../../2014/reporting-services/media/customreportitemrun-timecomponentarchitecture.gif "Custom report item run-time component")</span></span>  
  
## <a name="the-design-time-component"></a><span data-ttu-id="6a680-110">O componente de tempo de design</span><span class="sxs-lookup"><span data-stu-id="6a680-110">The Design-Time Component</span></span>  
 <span data-ttu-id="6a680-111">O componente de tempo de design permite que o item de relatório personalizado seja definido e manipulado na interface do Designer de Relatórios em [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6a680-111">The design-time component allows the custom report item to be defined and manipulated in the Report Designer interface in [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="6a680-112">O componente de tempo de design consiste em vários subcontroles que controlam a aparência e as propriedades do item de relatório personalizado no ambiente de design.</span><span class="sxs-lookup"><span data-stu-id="6a680-112">The design-time component consists of several sub-controls that control the appearance and properties of the custom report item in the design environment.</span></span>  
  
 <span data-ttu-id="6a680-113">![Componente de tempo de design de item de relatório personalizado](../../../2014/reporting-services/media/customreportitemdesign-timecomponentarchitecture.gif "Componente de tempo de design de item de relatório personalizado")</span><span class="sxs-lookup"><span data-stu-id="6a680-113">![Custom report item design-time component](../../../2014/reporting-services/media/customreportitemdesign-timecomponentarchitecture.gif "Custom report item design-time component")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a680-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6a680-114">See Also</span></span>  
 <span data-ttu-id="6a680-115">[Criando um componente de tempo de execução de item de relatório personalizado](../custom-report-items/creating-a-custom-report-item-run-time-component.md) </span><span class="sxs-lookup"><span data-stu-id="6a680-115">[Creating a Custom Report Item Run-Time Component](../custom-report-items/creating-a-custom-report-item-run-time-component.md) </span></span>  
 <span data-ttu-id="6a680-116">[Criando um componente de item de relatório personalizado em tempo de design](../custom-report-items/creating-a-custom-report-item-design-time-component.md) </span><span class="sxs-lookup"><span data-stu-id="6a680-116">[Creating a Custom Report Item Design-Time Component](../custom-report-items/creating-a-custom-report-item-design-time-component.md) </span></span>  
 [<span data-ttu-id="6a680-117">Como: implantar um Item de relatório personalizado</span><span class="sxs-lookup"><span data-stu-id="6a680-117">How to: Deploy a Custom Report Item</span></span>](../custom-report-items/how-to-deploy-a-custom-report-item.md)  
  
  
