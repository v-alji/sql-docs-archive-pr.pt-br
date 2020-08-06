---
title: Implementando uma extensão de renderização | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- rendering extensions [Reporting Services]
- custom rendering extensions [Reporting Services]
- transformations [Reporting Services]
- extensions [Reporting Services], rendering
- rendering extensions [Reporting Services], implementing
ms.assetid: 4a5c64f5-2391-4597-ba3f-81d265b23703
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 03deb7c818de8d875f69b585ae6015fc178e707d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574535"
---
# <a name="implementing-a-rendering-extension"></a><span data-ttu-id="e9c7c-102">Implementando uma extensão de renderização</span><span class="sxs-lookup"><span data-stu-id="e9c7c-102">Implementing a Rendering Extension</span></span>
  <span data-ttu-id="e9c7c-103">Uma extensão de renderização é um componente ou um módulo de um servidor de relatório que transforma dados de relatório e informações de layout para um formato específico do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e9c7c-103">A rendering extension is a component or module of a report server that transforms report data and layout information into a device-specific format.</span></span> <span data-ttu-id="e9c7c-104">O SQL Server Reporting Services inclui seis extensões de renderização: HTML, Excel, Word, CSV ou Texto, XML, Imagem e PDF.</span><span class="sxs-lookup"><span data-stu-id="e9c7c-104">SQL Server Reporting Services includes six rendering extensions: HTML, Excel, Word, CSV or Text, XML, Image, and PDF.</span></span> <span data-ttu-id="e9c7c-105">Você pode criar extensões de renderização adicionais para gerar relatórios em outros formatos.</span><span class="sxs-lookup"><span data-stu-id="e9c7c-105">You can create additional rendering extensions to generate reports in other formats.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e9c7c-106">Para determinar quais extensões de renderização estão disponíveis, exiba a lista das extensões instaladas no arquivo RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="e9c7c-106">To determine which rendering extensions are available, you can view the list of installed extensions in the RSReportServer.config file.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e9c7c-107">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="e9c7c-107">In This Section</span></span>  
 [<span data-ttu-id="e9c7c-108">Visão geral das extensões de renderização</span><span class="sxs-lookup"><span data-stu-id="e9c7c-108">Rendering Extensions Overview</span></span>](rendering-extensions-overview.md)  
 <span data-ttu-id="e9c7c-109">Introduz como escrever uma extensão de renderização personalizada para o [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9c7c-109">Introduces how to write a custom rendering extension for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="e9c7c-110">Implementar a interface IRenderingExtension</span><span class="sxs-lookup"><span data-stu-id="e9c7c-110">Implementing the IRenderingExtension Interface</span></span>](implementing-the-irenderingextension-interface.md)  
 <span data-ttu-id="e9c7c-111">Descreve os atributos de uma extensão de renderização.</span><span class="sxs-lookup"><span data-stu-id="e9c7c-111">Describes the attributes of a rendering extension.</span></span>  
  
 [<span data-ttu-id="e9c7c-112">Implantando uma extensão de renderização</span><span class="sxs-lookup"><span data-stu-id="e9c7c-112">Deploying a Rendering Extension</span></span>](deploying-a-rendering-extension.md)  
 <span data-ttu-id="e9c7c-113">Descreve como implantar uma extensão de renderização em um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="e9c7c-113">Describes how to deploy a rendering extension on a report server.</span></span>  
  
 [<span data-ttu-id="e9c7c-114">Remover uma extensão de renderização</span><span class="sxs-lookup"><span data-stu-id="e9c7c-114">Removing a Rendering Extension</span></span>](removing-a-rendering-extension.md)  
 <span data-ttu-id="e9c7c-115">Descreve como remover uma extensão de renderização de um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="e9c7c-115">Describes how to remove a rendering extension from a report server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9c7c-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e9c7c-116">See Also</span></span>  
 <span data-ttu-id="e9c7c-117">[Extensões do Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="e9c7c-117">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 [<span data-ttu-id="e9c7c-118">Biblioteca de extensões do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="e9c7c-118">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
