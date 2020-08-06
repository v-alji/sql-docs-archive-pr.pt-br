---
title: Tarefa de Upload do Blob do Azure | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpblobuptask.f1
- sql11.dts.designer.afpblobuptask.f1
ms.assetid: 6ea068b0-4cd8-45b5-b89d-09b8f25040c0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0ca15c5a77a2694293981121f4e5927be8ec0e1c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679472"
---
# <a name="azure-blob-upload-task"></a><span data-ttu-id="8ee32-102">Tarefa de Carregamento de Blobs do Azure</span><span class="sxs-lookup"><span data-stu-id="8ee32-102">Azure Blob Upload Task</span></span>
  <span data-ttu-id="8ee32-103">A Tarefa de Carregamento de Blobs do Azure permite que um pacote SSIS carregue arquivos para um armazenamento de blobs do Azure.</span><span class="sxs-lookup"><span data-stu-id="8ee32-103">The Azure Blob Upload Task enables an SSIS package to upload files to an Azure blob storage.</span></span>   
<span data-ttu-id="8ee32-104">Para adicionar uma **Tarefa de Upload de Blobs do Azure**, arraste-a e solte-a no Designer SSIS, e clique duas vezes ou com o botão direito do mouse em **Editar** para ver a caixa de diálogo **Editor da Tarefa de Upload de Blobs do Azure** .</span><span class="sxs-lookup"><span data-stu-id="8ee32-104">To add an **Azure Blob Upload Task**, drag-drop it to the SSIS Designer, and double-click or right-click and click **Edit** to see the following **Azure Blob Upload Task Editor** dialog box.</span></span>  
  
 <span data-ttu-id="8ee32-105">A tabela a seguir fornece descrições para os campos nessa caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="8ee32-105">The following table provides descriptions for the fields in this dialog box.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8ee32-106">**Campo**</span><span class="sxs-lookup"><span data-stu-id="8ee32-106">**Field**</span></span>|<span data-ttu-id="8ee32-107">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="8ee32-107">**Description**</span></span>|  
|<span data-ttu-id="8ee32-108">AzureStorageConnection</span><span class="sxs-lookup"><span data-stu-id="8ee32-108">AzureStorageConnection</span></span>|<span data-ttu-id="8ee32-109">Especifique um Gerenciador de Conexão de Armazenamento do Azure existente ou crie um novo referindo-se a uma Conta de Armazenamento do Azure, que aponta para onde os arquivos de blob estão hospedados.</span><span class="sxs-lookup"><span data-stu-id="8ee32-109">Specify an existing Azure Storage Connection Manager or create a new one that refers to an Azure Storage Account, which points to where the blob files are hosted.</span></span>|  
|<span data-ttu-id="8ee32-110">BlobContainer</span><span class="sxs-lookup"><span data-stu-id="8ee32-110">BlobContainer</span></span>|<span data-ttu-id="8ee32-111">Especifica o nome do contêiner de blobs que conterá os arquivos carregados como blobs.</span><span class="sxs-lookup"><span data-stu-id="8ee32-111">Specifies the name of the blob container that will hold the uploaded files as blobs.</span></span>|  
|<span data-ttu-id="8ee32-112">BlobDirectory</span><span class="sxs-lookup"><span data-stu-id="8ee32-112">BlobDirectory</span></span>|<span data-ttu-id="8ee32-113">Especifica o diretório de blob onde o arquivo carregado será armazenado como um blob de blocos.</span><span class="sxs-lookup"><span data-stu-id="8ee32-113">Specifies the blob directory where the uploaded file will be stored as a block blob.</span></span> <span data-ttu-id="8ee32-114">O diretório de blob é uma estrutura hierárquica virtual.</span><span class="sxs-lookup"><span data-stu-id="8ee32-114">The blob directory is a virtual hierarchical structure.</span></span> <span data-ttu-id="8ee32-115">Se o blob já existir, ele será substituído.</span><span class="sxs-lookup"><span data-stu-id="8ee32-115">If the blob already exists, it will be replaced.</span></span>|  
|<span data-ttu-id="8ee32-116">LocalDirectory</span><span class="sxs-lookup"><span data-stu-id="8ee32-116">LocalDirectory</span></span>|<span data-ttu-id="8ee32-117">Especifique o diretório local que contém os arquivos a serem carregados.</span><span class="sxs-lookup"><span data-stu-id="8ee32-117">Specify the local directory that contains the files to be uploaded.</span></span>|  
|<span data-ttu-id="8ee32-118">FileName</span><span class="sxs-lookup"><span data-stu-id="8ee32-118">FileName</span></span>|<span data-ttu-id="8ee32-119">Especifica um filtro de nome para selecionar arquivos com o padrão de nome especificado.</span><span class="sxs-lookup"><span data-stu-id="8ee32-119">Specifies a name filter to select files with the specified name pattern.</span></span> <span data-ttu-id="8ee32-120">Por ex.:</span><span class="sxs-lookup"><span data-stu-id="8ee32-120">E.g.</span></span> <span data-ttu-id="8ee32-121">MySheet\*.xls\* inclui arquivos como MySheet001.xls e MySheetABC.xlsx.</span><span class="sxs-lookup"><span data-stu-id="8ee32-121">MySheet\*.xls\* includes files such as MySheet001.xls and MySheetABC.xlsx.</span></span>|  
|<span data-ttu-id="8ee32-122">TimeRangeFrom/TimeRangeTo</span><span class="sxs-lookup"><span data-stu-id="8ee32-122">TimeRangeFrom/TimeRangeTo</span></span>|<span data-ttu-id="8ee32-123">Especifica um filtro de intervalo de tempo.</span><span class="sxs-lookup"><span data-stu-id="8ee32-123">Specifies a time range filter.</span></span> <span data-ttu-id="8ee32-124">Arquivos modificados após **TimeRangeFrom** e antes de **TimeRangeTo** serão incluídos.</span><span class="sxs-lookup"><span data-stu-id="8ee32-124">Files modified after **TimeRangeFrom** and before **TimeRangeTo** will be included.</span></span>|  
  
  
