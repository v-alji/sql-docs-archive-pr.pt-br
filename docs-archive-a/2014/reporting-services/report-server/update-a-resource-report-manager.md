---
title: Atualizar um recurso (Gerenciador de Relatórios) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- updating resources
- resources [Reporting Services], updating
ms.assetid: d21f7493-bcf7-4e9e-9886-55ebdc1f1037
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a0fca59e476c2820b715ff46729784edc562f74d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573620"
---
# <a name="update-a-resource-report-manager"></a><span data-ttu-id="98998-102">Atualizar um recurso (Gerenciador de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="98998-102">Update a Resource (Report Manager)</span></span>
  <span data-ttu-id="98998-103">É possível atualizar um recurso substituindo-o por uma versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="98998-103">You can update a resource by replacing it with a newer version.</span></span> <span data-ttu-id="98998-104">Recursos são itens armazenados em um servidor de relatório com conteúdo de um arquivo carregado pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="98998-104">Resources are items stored on a report server that contain content from a file that you upload.</span></span> <span data-ttu-id="98998-105">Você pode substituir um recurso existente importando conteúdo de arquivo novo ou diferente no recurso existente.</span><span class="sxs-lookup"><span data-stu-id="98998-105">You can replace an existing resource by importing new or different file content into the existing resource.</span></span> <span data-ttu-id="98998-106">A atualização de um recurso fornece um modo de atualizar conteúdo e ao mesmo tempo preservar as propriedades e configurações de segurança já existentes no recurso.</span><span class="sxs-lookup"><span data-stu-id="98998-106">Updating a resource provides a way to update content while preserving existing properties and security settings on the resource.</span></span>  
  
### <a name="to-update-a-resource"></a><span data-ttu-id="98998-107">Para atualizar um recurso</span><span class="sxs-lookup"><span data-stu-id="98998-107">To update a resource</span></span>  
  
1.  <span data-ttu-id="98998-108">Inicie o [Gerenciador de Relatórios &#40;Modo Nativo do SSRS&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="98998-108">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="98998-109">No Gerenciador de Relatórios, navegue até ou procure o recurso que deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="98998-109">In Report Manager, navigate to or search for the resource you want to update.</span></span>  
  
3.  <span data-ttu-id="98998-110">Clique no recurso para abri-lo na página **Exibir** .</span><span class="sxs-lookup"><span data-stu-id="98998-110">Click the resource to open it in the **View** page.</span></span>  
  
4.  <span data-ttu-id="98998-111">Clique em **Propriedades** para abrir a página **Propriedades Gerais** .</span><span class="sxs-lookup"><span data-stu-id="98998-111">Click **Properties** to open the **General** properties page.</span></span>  
  
5.  <span data-ttu-id="98998-112">Clique em **Substituir** para abrir a página **Importar Recurso** .</span><span class="sxs-lookup"><span data-stu-id="98998-112">Click **Replace** to open the **Import Resource** page.</span></span>  
  
6.  <span data-ttu-id="98998-113">Clique em **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="98998-113">Click **Browse**.</span></span>  
  
7.  <span data-ttu-id="98998-114">Selecione o arquivo que deseja usar para substituir o recurso atual.</span><span class="sxs-lookup"><span data-stu-id="98998-114">Select the file that you want to use to replace the current resource.</span></span> <span data-ttu-id="98998-115">Você pode usar uma versão atualizada do arquivo do recurso ou especificar um arquivo com um nome ou tipo de arquivo diferente.</span><span class="sxs-lookup"><span data-stu-id="98998-115">You can use an updated version of the resource file, or specify a file with a different name or file type.</span></span>  
  
8.  <span data-ttu-id="98998-116">Clique em **OK** para carregar o arquivo do recurso, feche a página **Importar Recurso** e salve as alterações no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="98998-116">Click **OK** to upload the resource file, close the **Import Resource** page, and save your changes to the report server.</span></span>  
  
 <span data-ttu-id="98998-117">Se o recurso que você está atualizando possuir uma imagem usada em um relatório, será necessário atualizar o relatório para visualizar a imagem atualizada.</span><span class="sxs-lookup"><span data-stu-id="98998-117">If the resource you are updating contains an image that is used in a report, you need to refresh the report to see the updated image.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98998-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="98998-118">See Also</span></span>  
 <span data-ttu-id="98998-119">[Página de conteúdo &#40;Report Manager&#41;](../contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="98998-119">[Contents Page &#40;Report Manager&#41;](../contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="98998-120">[&#40;Report Manager de carregamento da página de arquivos&#41;](../upload-file-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="98998-120">[Upload File Page &#40;Report Manager&#41;](../upload-file-page-report-manager.md) </span></span>  
 <span data-ttu-id="98998-121">[Carregar arquivos em uma pasta](upload-files-to-a-folder.md) </span><span class="sxs-lookup"><span data-stu-id="98998-121">[Upload Files to a Folder](upload-files-to-a-folder.md) </span></span>  
 [<span data-ttu-id="98998-122">Ajuda F1 do Gerenciador de Relatórios</span><span class="sxs-lookup"><span data-stu-id="98998-122">Report Manager F1 Help</span></span>](../report-manager-f1-help.md)  
  
  
