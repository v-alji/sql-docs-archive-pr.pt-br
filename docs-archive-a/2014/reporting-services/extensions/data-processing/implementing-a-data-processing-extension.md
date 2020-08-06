---
title: Implementando uma extensão de processamento de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom data processing extensions [Reporting Services]
- data sources [Reporting Services], data processing extensions
- data processing extensions [Reporting Services]
- extensions [Reporting Services], data processing
ms.assetid: 8dc2b44e-5ad9-411d-a29f-7213e29321a9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5a1b7668f2319e742dcf3f1969fc3c5cc85cd7eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685441"
---
# <a name="implementing-a-data-processing-extension"></a><span data-ttu-id="ccbd4-102">Implementando uma extensão de processamento de dados</span><span class="sxs-lookup"><span data-stu-id="ccbd4-102">Implementing a Data Processing Extension</span></span>
  <span data-ttu-id="ccbd4-103">As extensões de processamento de dados do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] permitem que você se conecte a uma fonte de dados e recupere dados.</span><span class="sxs-lookup"><span data-stu-id="ccbd4-103">Data processing extensions in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] enable you to connect to a data source and retrieve data.</span></span> <span data-ttu-id="ccbd4-104">Eles também servem como uma ponte entre uma fonte de dados e um conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="ccbd4-104">They also serve as a bridge between a data source and a dataset.</span></span> <span data-ttu-id="ccbd4-105">As extensões de processamento de dados do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] são modeladas de acordo com um subconjunto das interfaces do provedor de dados do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ccbd4-105">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extensions are modeled after a subset of the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] data provider interfaces.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ccbd4-106">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="ccbd4-106">In This Section</span></span>  
 [<span data-ttu-id="ccbd4-107">Visão geral das extensões de processamento de dados</span><span class="sxs-lookup"><span data-stu-id="ccbd4-107">Data Processing Extensions Overview</span></span>](data-processing-extensions-overview.md)  
 <span data-ttu-id="ccbd4-108">Apresenta como escrever uma extensão de processamento de dados personalizada para o [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ccbd4-108">Introduces how to write a custom data processing extension for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="ccbd4-109">Preparar a implementação de uma extensão de processamento de dados</span><span class="sxs-lookup"><span data-stu-id="ccbd4-109">Preparing to Implement a Data Processing Extension</span></span>](preparing-to-implement-a-data-processing-extension.md)  
 <span data-ttu-id="ccbd4-110">Descreve as interfaces disponíveis durante a implementação de uma extensão de processamento de dados do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], como também quando você precisa implementar uma interface específica.</span><span class="sxs-lookup"><span data-stu-id="ccbd4-110">Describes the interfaces available when implementing an [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extension, as well as when you are required to implement a particular interface.</span></span>  
  
 [<span data-ttu-id="ccbd4-111">Criar uma biblioteca de extensões de processamento de dados</span><span class="sxs-lookup"><span data-stu-id="ccbd4-111">Creating a Data Processing Extension Library</span></span>](creating-a-data-processing-extension-library.md)  
 <span data-ttu-id="ccbd4-112">Descreve a atribuição de um namespace para a sua extensão de processamento de dados do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] e a compilação da sua extensão de processamento de dados em uma DLL de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="ccbd4-112">Describes assigning a namespace for your [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extension and compiling your data processing extension into a library DLL.</span></span>  
  
 [<span data-ttu-id="ccbd4-113">Implementar uma classe Connection para uma extensão de processamento de dados</span><span class="sxs-lookup"><span data-stu-id="ccbd4-113">Implementing a Connection Class for a Data Processing Extension</span></span>](implementing-a-connection-class-for-a-data-processing-extension.md)  
 <span data-ttu-id="ccbd4-114">Descreve os atributos de uma conexão e como implementar sua própria classe **Connection** para a extensão de processamento de dados.</span><span class="sxs-lookup"><span data-stu-id="ccbd4-114">Describes the attributes of a connection and how to implement your own **Connection** class for your data processing extension.</span></span>  
  
 [<span data-ttu-id="ccbd4-115">Implementar uma classe Command para uma extensão de processamento de dados</span><span class="sxs-lookup"><span data-stu-id="ccbd4-115">Implementing a Command Class for a Data Processing Extension</span></span>](implementing-a-command-class-for-a-data-processing-extension.md)  
 <span data-ttu-id="ccbd4-116">Descreve os atributos de um comando e como implementar sua própria classe **Command** para a extensão de processamento de dados.</span><span class="sxs-lookup"><span data-stu-id="ccbd4-116">Describes the attributes of a command, and how to implement your own **Command** class for your data processing extension.</span></span>  
  
 [<span data-ttu-id="ccbd4-117">Implementar uma classe DataReader para uma extensão de processamento de dados</span><span class="sxs-lookup"><span data-stu-id="ccbd4-117">Implementing a DataReader Class for a Data Processing Extension</span></span>](implementing-a-datareader-class-for-a-data-processing-extension.md)  
 <span data-ttu-id="ccbd4-118">Descreve os atributos de um leitor de dados e como implementar sua própria classe **DataReader** para a extensão de processamento de dados.</span><span class="sxs-lookup"><span data-stu-id="ccbd4-118">Describes the attributes of a data reader and how to implement your own **DataReader** class for your data processing extension.</span></span>  
  
 [<span data-ttu-id="ccbd4-119">Usar um conjunto de dados externo com o Reporting Services</span><span class="sxs-lookup"><span data-stu-id="ccbd4-119">Using an External Dataset with Reporting Services</span></span>](using-an-external-dataset-with-reporting-services.md)  
 <span data-ttu-id="ccbd4-120">Descreve como expor os objetos **DataSet** personalizados para o servidor de relatório para consumo.</span><span class="sxs-lookup"><span data-stu-id="ccbd4-120">Describes how to expose your custom **DataSet** objects to the report server for consumption.</span></span>  
  
 [<span data-ttu-id="ccbd4-121">Implantando uma extensão de processamento de dados</span><span class="sxs-lookup"><span data-stu-id="ccbd4-121">Deploying a Data Processing Extension</span></span>](deploying-a-data-processing-extension.md)  
 <span data-ttu-id="ccbd4-122">Descreve como implantar a sua extensão de processamento de dados.</span><span class="sxs-lookup"><span data-stu-id="ccbd4-122">Describes how to deploy your data processing extension.</span></span>  
  
 [<span data-ttu-id="ccbd4-123">Depurar o código de extensão de processamento de dados</span><span class="sxs-lookup"><span data-stu-id="ccbd4-123">Debugging Data Processing Extension Code</span></span>](debugging-data-processing-extension-code.md)  
 <span data-ttu-id="ccbd4-124">Descreve como depurar código em suas extensões de processamento de dados.</span><span class="sxs-lookup"><span data-stu-id="ccbd4-124">Describes how to debug code in your data processing extensions.</span></span>  
  
 [<span data-ttu-id="ccbd4-125">Removendo uma extensão de processamento de dados</span><span class="sxs-lookup"><span data-stu-id="ccbd4-125">Removing a Data Processing Extension</span></span>](removing-a-data-processing-extension.md)  
 <span data-ttu-id="ccbd4-126">Descreve como remover uma extensão de processamento de dados de um servidor de relatório ou do Designer de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="ccbd4-126">Describes how to remove a data processing extension from a report server or Report Designer.</span></span>  
  
 <span data-ttu-id="ccbd4-127">Para obter uma amostra de uma extensão de processamento de dados totalmente implementada, consulte [Amostras de produto do SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="ccbd4-127">For a sample of a fully implemented data processing extension, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccbd4-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ccbd4-128">See Also</span></span>  
 <span data-ttu-id="ccbd4-129">[Extensões de Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="ccbd4-129">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 [<span data-ttu-id="ccbd4-130">Biblioteca de extensões do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="ccbd4-130">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
