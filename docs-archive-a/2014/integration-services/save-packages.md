---
title: Salvar pacotes | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services packages, saving
- packages [Integration Services], saving
- saving packages
- SSIS packages, saving
- SQL Server Integration Services packages, saving
ms.assetid: 17c1de2c-637f-45c2-a148-79294bae0af4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 102e2c3eab001c230722bf3485d6ea9731aa99a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684258"
---
# <a name="save-packages"></a><span data-ttu-id="bfd4c-102">Salvar pacotes</span><span class="sxs-lookup"><span data-stu-id="bfd4c-102">Save Packages</span></span>
  <span data-ttu-id="bfd4c-103">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , você cria pacotes usando o Designer do [!INCLUDE[ssIS](../includes/ssis-md.md)] e salva os pacotes no sistema de arquivos como arquivos XML (arquivos .dtsx).</span><span class="sxs-lookup"><span data-stu-id="bfd4c-103">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] you build packages by using [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer and save the packages to the file system as XML files (.dtsx files).</span></span> <span data-ttu-id="bfd4c-104">Você também pode salvar cópias do arquivo XML de pacote no banco de dados msdb no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ou no repositório de pacotes.</span><span class="sxs-lookup"><span data-stu-id="bfd4c-104">You can also save copies of the package XML file to the msdb database in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] or to the package store.</span></span> <span data-ttu-id="bfd4c-105">O repositório de pacotes representa as pastas no local do sistema de arquivos que o serviço do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] gerencia.</span><span class="sxs-lookup"><span data-stu-id="bfd4c-105">The package store represents the folders in the file system location that the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service manages.</span></span>  
  
 <span data-ttu-id="bfd4c-106">Se você salvar um pacote no sistema de arquivos, poderá depois usar o serviço do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] para importar o pacote para o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ou para o armazenamento de pacotes.</span><span class="sxs-lookup"><span data-stu-id="bfd4c-106">If you save a package to the file system, you can later use the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service to import the package to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] or to the package store.</span></span> <span data-ttu-id="bfd4c-107">Para obter mais informações, consulte [Importar e exportar pacotes &#40;Serviço SSIS&#41;](../../2014/integration-services/import-and-export-packages-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="bfd4c-107">For more information, see [Import and Export Packages &#40;SSIS Service&#41;](../../2014/integration-services/import-and-export-packages-ssis-service.md).</span></span>  
  
 <span data-ttu-id="bfd4c-108">Você também pode usar um utilitário de prompt de comando, **dtutil**, para copiar um pacote entre o sistema de arquivos e o msdb.</span><span class="sxs-lookup"><span data-stu-id="bfd4c-108">You can also use a command prompt utility, **dtutil**, to copy a package between the file system and msdb.</span></span> <span data-ttu-id="bfd4c-109">Para obter mais informações, consulte [dtutil Utility](dtutil-utility.md).</span><span class="sxs-lookup"><span data-stu-id="bfd4c-109">For more information, see [dtutil Utility](dtutil-utility.md).</span></span>  
  
### <a name="to-save-a-package"></a><span data-ttu-id="bfd4c-110">Para salvar um pacote</span><span class="sxs-lookup"><span data-stu-id="bfd4c-110">To save a package</span></span>  
  
-   [<span data-ttu-id="bfd4c-111">Salvar um pacote no sistema de arquivos</span><span class="sxs-lookup"><span data-stu-id="bfd4c-111">Save a Package to the File System</span></span>](../../2014/integration-services/save-a-package-to-the-file-system.md)  
  
-   [<span data-ttu-id="bfd4c-112">Salvar uma cópia de um pacote</span><span class="sxs-lookup"><span data-stu-id="bfd4c-112">Save a Copy of a Package</span></span>](../../2014/integration-services/save-a-copy-of-a-package.md)  
  
  
