---
title: Tarefa de Download do Blob do Azure | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpblobdltask.f1
- sql11.dts.designer.afpblobdltask.f1
ms.assetid: 8a63bf44-71be-456d-9a5c-be7c31aff065
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e2f61260b1fceaad3c27a0ce6ab6af28b15582bc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679473"
---
# <a name="azure-blob-download-task"></a><span data-ttu-id="8d916-102">Tarefa de Download do Blob do Azure</span><span class="sxs-lookup"><span data-stu-id="8d916-102">Azure Blob Download Task</span></span>
  <span data-ttu-id="8d916-103">A Tarefa de Download do Blob do Azure permite que um pacote SSIS baixe arquivos de um armazenamento de blob do Azure.</span><span class="sxs-lookup"><span data-stu-id="8d916-103">The Azure Blob Download Task enables an SSIS package to download files from an Azure blob storage.</span></span>   
<span data-ttu-id="8d916-104">Para adicionar uma **Tarefa de Download de Blobs do Azure**, arraste-a e solte-a no Designer SSIS, e clique duas vezes ou com o botão direito do mouse em **Editar** para ver a caixa de diálogo **Editor da Tarefa de Download de Blobs do Azure** .</span><span class="sxs-lookup"><span data-stu-id="8d916-104">To add an **Azure Blob Download Task**, drag-drop it to the SSIS Designer, and double-click or right-click and click **Edit** to see the following **Azure Blob Download Task Editor** dialog box.</span></span>  
  
 <span data-ttu-id="8d916-105">A tabela a seguir fornece uma descrição para os campos nessa caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="8d916-105">The following table provides description for the fields in this dialog box.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8d916-106">**Campo**</span><span class="sxs-lookup"><span data-stu-id="8d916-106">**Field**</span></span>|<span data-ttu-id="8d916-107">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="8d916-107">**Description**</span></span>|  
|<span data-ttu-id="8d916-108">AzureStorageConnection</span><span class="sxs-lookup"><span data-stu-id="8d916-108">AzureStorageConnection</span></span>|<span data-ttu-id="8d916-109">Especifique um Gerenciador de Conexão de Armazenamento do Azure existente ou crie um novo referindo-se a uma Conta de Armazenamento do Azure, que aponta para onde os arquivos de blob estão hospedados.</span><span class="sxs-lookup"><span data-stu-id="8d916-109">Specify an existing Azure Storage Connection Manager or create a new one that refers to an Azure Storage Account, which points to where the blob files are hosted.</span></span>|  
|<span data-ttu-id="8d916-110">BlobContainer</span><span class="sxs-lookup"><span data-stu-id="8d916-110">BlobContainer</span></span>|<span data-ttu-id="8d916-111">Especifica o nome do contêiner de Blob que contém os arquivos de Blob a serem baixados.</span><span class="sxs-lookup"><span data-stu-id="8d916-111">Specifies the name of the blob container that contains the blob files to be downloaded.</span></span>|  
|<span data-ttu-id="8d916-112">BlobDirectory</span><span class="sxs-lookup"><span data-stu-id="8d916-112">BlobDirectory</span></span>|<span data-ttu-id="8d916-113">Especifica o diretório de Blob que contém os arquivos de Blob a serem baixados.</span><span class="sxs-lookup"><span data-stu-id="8d916-113">Specifies the blob directory that contains the blob files to be downloaded.</span></span> <span data-ttu-id="8d916-114">O diretório de blob é uma estrutura hierárquica virtual.</span><span class="sxs-lookup"><span data-stu-id="8d916-114">The blob directory is a virtual hierarchical structure.</span></span>|  
|<span data-ttu-id="8d916-115">LocalDirectory</span><span class="sxs-lookup"><span data-stu-id="8d916-115">LocalDirectory</span></span>|<span data-ttu-id="8d916-116">Especifica o diretório local onde serão armazenados os arquivos de blob baixados.</span><span class="sxs-lookup"><span data-stu-id="8d916-116">Specifies the local directory where the downloaded blob files will be stored.</span></span>|  
|<span data-ttu-id="8d916-117">FileName</span><span class="sxs-lookup"><span data-stu-id="8d916-117">FileName</span></span>|<span data-ttu-id="8d916-118">Especifica um filtro de nome para selecionar arquivos com o padrão de nome especificado.</span><span class="sxs-lookup"><span data-stu-id="8d916-118">Specifies a name filter to select files with the specified name pattern.</span></span> <span data-ttu-id="8d916-119">Por ex.:</span><span class="sxs-lookup"><span data-stu-id="8d916-119">E.g.</span></span> <span data-ttu-id="8d916-120">MySheet\*.xls\* inclui arquivos como MySheet001.xls e MySheetABC.xlsx.</span><span class="sxs-lookup"><span data-stu-id="8d916-120">MySheet\*.xls\* includes files such as MySheet001.xls and MySheetABC.xlsx.</span></span>|  
|<span data-ttu-id="8d916-121">TimeRangeFrom/TimeRangeTo</span><span class="sxs-lookup"><span data-stu-id="8d916-121">TimeRangeFrom/TimeRangeTo</span></span>|<span data-ttu-id="8d916-122">Especifica um filtro de intervalo de tempo.</span><span class="sxs-lookup"><span data-stu-id="8d916-122">Specifies a time range filter.</span></span> <span data-ttu-id="8d916-123">Arquivos modificados após **TimeRangeFrom** e antes de **TimeRangeTo** serão incluídos.</span><span class="sxs-lookup"><span data-stu-id="8d916-123">Files modified after **TimeRangeFrom** and before **TimeRangeTo** will be included.</span></span>|  
  
  
