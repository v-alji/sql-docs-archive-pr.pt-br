---
title: Carregar um arquivo ou relatório (Gerenciador de Relatórios) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- publishing reports [Reporting Services], uploading files
- reports [Reporting Services], publishing
- uploading reports [Reporting Services]
- uploading files [Reporting Services]
- files [Reporting Services], uploading
ms.assetid: 79027e11-f4ba-4bfd-bd8c-d334e3da02a1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 119e2b22976dc227e017b81a59b698cf9eb7457f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571286"
---
# <a name="upload-a-file-or-report-report-manager"></a><span data-ttu-id="d098a-102">Carregar um arquivo ou relatório (Gerenciador de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="d098a-102">Upload a File or Report (Report Manager)</span></span>
  <span data-ttu-id="d098a-103">O Gerenciador de Relatórios fornece um recurso de carregamento que permite adicionar relatórios, modelos e outros arquivos a um servidor de relatório sem publicar esses itens a partir de um aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="d098a-103">Report Manager provides an upload feature so that you can add reports, models, and other files to a report server without having to publish those items from a client application.</span></span> <span data-ttu-id="d098a-104">Os arquivos carregados a partir do sistema de arquivos são armazenados como itens no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="d098a-104">Files that you upload from the file system are stored as items on the report server.</span></span> <span data-ttu-id="d098a-105">O tipo de arquivo carregado determina o modo de armazenamento:</span><span class="sxs-lookup"><span data-stu-id="d098a-105">The type of file you upload determines how it is stored:</span></span>  
  
-   <span data-ttu-id="d098a-106">Os arquivos .rdl são armazenados como relatórios.</span><span class="sxs-lookup"><span data-stu-id="d098a-106">.rdl files are stored as reports.</span></span>  
  
-   <span data-ttu-id="d098a-107">Os arquivos .smdl são armazenados como modelos de relatório.</span><span class="sxs-lookup"><span data-stu-id="d098a-107">.smdl files are stored as report models.</span></span>  
  
-   <span data-ttu-id="d098a-108">Todos os outros arquivos, incluindo os arquivos de fonte de dados compartilhada (.rds), são carregados como recursos.</span><span class="sxs-lookup"><span data-stu-id="d098a-108">All other files, including shared data source (.rds) files, are uploaded as resources.</span></span> <span data-ttu-id="d098a-109">Os recursos não são processados por um servidor de relatório, mas podem ser exibidos no Gerenciador de Relatórios se o servidor de relatório oferecer suporte ao tipo MIME de arquivo.</span><span class="sxs-lookup"><span data-stu-id="d098a-109">Resources are not processed by a report server, but can be viewed in Report Manager if the report server supports the MIME type of the file.</span></span>  
  
### <a name="to-upload-a-file-or-report"></a><span data-ttu-id="d098a-110">Para carregar um arquivo ou relatório</span><span class="sxs-lookup"><span data-stu-id="d098a-110">To upload a file or report</span></span>  
  
1.  <span data-ttu-id="d098a-111">Inicie o [Gerenciador de Relatórios &#40;Modo Nativo do SSRS&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="d098a-111">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="d098a-112">Em Report Manager, navegue até a página **conteúdo** .</span><span class="sxs-lookup"><span data-stu-id="d098a-112">In Report Manager, navigate to the **Contents** page.</span></span> <span data-ttu-id="d098a-113">Navegue até a pasta à qual deseja adicionar um item.</span><span class="sxs-lookup"><span data-stu-id="d098a-113">Navigate to the folder to which you want to add an item.</span></span>  
  
3.  <span data-ttu-id="d098a-114">Clique em **Carregar Arquivo**.</span><span class="sxs-lookup"><span data-stu-id="d098a-114">Click **Upload File**.</span></span>  
  
4.  <span data-ttu-id="d098a-115">Clique em **Procurar** para selecionar o arquivo a ser carregado.</span><span class="sxs-lookup"><span data-stu-id="d098a-115">Click **Browse** to select a file to upload.</span></span> <span data-ttu-id="d098a-116">Você pode carregar um arquivo de definição de relatório, uma imagem, um documento ou qualquer arquivo que deseje disponibilizar no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="d098a-116">You can upload a report definition file, an image, a document, or any file that you want to make available on the report server.</span></span>  
  
5.  <span data-ttu-id="d098a-117">Digite um nome para o novo item.</span><span class="sxs-lookup"><span data-stu-id="d098a-117">Type a name for the new item.</span></span> <span data-ttu-id="d098a-118">Um nome de item pode incluir espaços, mas não pode incluir os caracteres reservados: ; ?</span><span class="sxs-lookup"><span data-stu-id="d098a-118">An item name can include spaces, but cannot include the reserved characters: ; ?</span></span> <span data-ttu-id="d098a-119">: \@ & = +, $/\* \< > |.</span><span class="sxs-lookup"><span data-stu-id="d098a-119">: \@ & = + , $ / \* \< > |.</span></span>  
  
6.  <span data-ttu-id="d098a-120">Se desejar substituir um item existente pelo novo item, selecione **Substituir item, se existir**.</span><span class="sxs-lookup"><span data-stu-id="d098a-120">If you want to replace an existing item with the new item, select **Overwrite item if it exists**.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d098a-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d098a-121">See Also</span></span>  
 <span data-ttu-id="d098a-122">[Criar, excluir ou modificar uma fonte de dados compartilhada &#40;Report Manager&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="d098a-122">[Create, Delete, or Modify a Shared Data Source &#40;Report Manager&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) </span></span>  
 <span data-ttu-id="d098a-123">[Página de conteúdo &#40;Report Manager&#41;](../contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="d098a-123">[Contents Page &#40;Report Manager&#41;](../contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="d098a-124">[&#40;Report Manager de carregamento da página de arquivos&#41;](../upload-file-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="d098a-124">[Upload File Page &#40;Report Manager&#41;](../upload-file-page-report-manager.md) </span></span>  
 [<span data-ttu-id="d098a-125">Carregar arquivos em uma pasta</span><span class="sxs-lookup"><span data-stu-id="d098a-125">Upload Files to a Folder</span></span>](../report-server/upload-files-to-a-folder.md)  
  
  
