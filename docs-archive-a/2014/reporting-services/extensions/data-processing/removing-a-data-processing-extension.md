---
title: Removendo uma extensão de processamento de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- deleting data processing extensions
- data processing extensions [Reporting Services], removing
- removing data processing extensions
ms.assetid: 1d89e32b-0631-44f6-8178-a57fb791d26d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9f5dfd3a6a7615fa3fd91c917bba6dbf0808f0f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685438"
---
# <a name="removing-a-data-processing-extension"></a><span data-ttu-id="d33d7-102">Removendo uma extensão de processamento de dados</span><span class="sxs-lookup"><span data-stu-id="d33d7-102">Removing a Data Processing Extension</span></span>
  <span data-ttu-id="d33d7-103">Para remover uma extensão de processamento de dados, basta remover o elemento **Extension** na extensão de processamento de dados do arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="d33d7-103">To remove a data processing extension, simply remove the **Extension** element for your data processing extension from the configuration file.</span></span> <span data-ttu-id="d33d7-104">Se você criou entradas para um servidor de relatório e para o Designer de Relatórios, remova o elemento **Extension** dos arquivos RSReportServer.config e RSReportDesigner.config.</span><span class="sxs-lookup"><span data-stu-id="d33d7-104">If you made entries for a report server as well as Report Designer, remove the **Extension** element from both the RSReportServer.config and RSReportDesigner.config files.</span></span> <span data-ttu-id="d33d7-105">Depois que as informações de configuração forem removidas, a extensão do processamento de dados não estará mais disponível para o componente.</span><span class="sxs-lookup"><span data-stu-id="d33d7-105">After the configuration information is removed, the data processing extension is no longer available to the component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d33d7-106">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d33d7-106">See Also</span></span>  
 <span data-ttu-id="d33d7-107">[Extensões de Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="d33d7-107">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="d33d7-108">[Implementando uma extensão de processamento de dados](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="d33d7-108">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="d33d7-109">Biblioteca de extensões do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="d33d7-109">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
