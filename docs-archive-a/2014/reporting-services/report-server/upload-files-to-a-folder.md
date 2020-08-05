---
title: Carregar arquivos em uma pasta | Microsoft Docs
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
- files [Reporting Services]
- folders [Reporting Services], uploading files to
ms.assetid: 2f99a288-d4aa-4c64-b310-e457a2aef2c5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cfb595ed6059436d17cb82262f5d1975a8397dbd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573619"
---
# <a name="upload-files-to-a-folder"></a><span data-ttu-id="a5b96-102">Carregar arquivos em uma pasta</span><span class="sxs-lookup"><span data-stu-id="a5b96-102">Upload Files to a Folder</span></span>
  <span data-ttu-id="a5b96-103">Você pode carregar arquivos do sistema de arquivos e armazená-los como itens gerenciados em um banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="a5b96-103">You can upload files from the file system and store them as managed items in a report server database.</span></span> <span data-ttu-id="a5b96-104">O que acontece quando o arquivo é carregado depende do tipo de arquivo.</span><span class="sxs-lookup"><span data-stu-id="a5b96-104">What happens when you upload a file depends on the file type.</span></span>

-   <span data-ttu-id="a5b96-105">Carregar um arquivo .rdl é equivalente a publicar um relatório.</span><span class="sxs-lookup"><span data-stu-id="a5b96-105">Uploading an .rdl file is equivalent to publishing a report.</span></span>

-   <span data-ttu-id="a5b96-106">O carregamento de qualquer outro arquivo adiciona esse arquivo ao banco de dados do servidor de relatório como um único objeto binário.</span><span class="sxs-lookup"><span data-stu-id="a5b96-106">Uploading any other file adds it to the report server database as a single binary object.</span></span> <span data-ttu-id="a5b96-107">Esses arquivos são publicados em um servidor de relatório como um recurso.</span><span class="sxs-lookup"><span data-stu-id="a5b96-107">These files are published to a report server as a resource.</span></span> <span data-ttu-id="a5b96-108">Os recursos podem ser qualquer tipo de arquivo.</span><span class="sxs-lookup"><span data-stu-id="a5b96-108">Resources can be any file type.</span></span> <span data-ttu-id="a5b96-109">Se a extensão do arquivo corresponder com um tipo MIME conhecido, um ícone desse tipo MIME será usado para identificar o tipo de recurso.</span><span class="sxs-lookup"><span data-stu-id="a5b96-109">If the file extension matches a known MIME type, an icon for that MIME type is used to identify the resource type.</span></span> <span data-ttu-id="a5b96-110">Caso contrário, um ícone de arquivo genérico indica um recurso.</span><span class="sxs-lookup"><span data-stu-id="a5b96-110">Otherwise, a generic file icon indicates a resource.</span></span>

> [!NOTE]
>  <span data-ttu-id="a5b96-111">Você não pode carregar um arquivo de fonte de dados de relatório (.rds) para criar uma fonte de dados compartilhada.</span><span class="sxs-lookup"><span data-stu-id="a5b96-111">You cannot upload a report data source (.rds) file to create a shared data source.</span></span> <span data-ttu-id="a5b96-112">Um arquivo .rds só é usado no Designer de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="a5b96-112">An .rds file is used only in Report Designer.</span></span> <span data-ttu-id="a5b96-113">Esse arquivo não pode fornecer o conteúdo para um item de fonte de dados compartilhada definido e gerenciado pelo Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="a5b96-113">It cannot provide the content for a shared data source item that you define and manage through Report Manager.</span></span> <span data-ttu-id="a5b96-114">Como alternativa do carregamento, é possível gravar um script que cria uma fonte de dados compartilhada com base em um arquivo .rds.</span><span class="sxs-lookup"><span data-stu-id="a5b96-114">As an alternative to uploading, you can write a script that creates a shared data source based on a .rds file.</span></span>

 <span data-ttu-id="a5b96-115">O tamanho de arquivo máximo para itens carregados é determinado por [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a5b96-115">The maximum file size for uploaded items is determined by [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)].</span></span> <span data-ttu-id="a5b96-116">Por padrão, o tamanho máximo é de 4 megabytes (MB).</span><span class="sxs-lookup"><span data-stu-id="a5b96-116">By default, the maximum size is 4 megabytes (MB).</span></span>

 <span data-ttu-id="a5b96-117">Visualmente, os arquivos carregados em um banco de dados do servidor de relatório são representados na hierarquia de pastas com os seguintes ícones.</span><span class="sxs-lookup"><span data-stu-id="a5b96-117">Visually, files that you upload to a report server database are represented in the folder hierarchy with the following icons.</span></span>

 <span data-ttu-id="a5b96-118">Ícone do relatório de ![ícone de relatório](../media/hlp-16doc.gif "Ícone de Relatório")</span><span class="sxs-lookup"><span data-stu-id="a5b96-118">![Report icon](../media/hlp-16doc.gif "Report icon") report icon</span></span>

 <span data-ttu-id="a5b96-119">Ícone ![modelo modelo de relatório ícone](../media/model-icon.gif "Ícone de modelo")</span><span class="sxs-lookup"><span data-stu-id="a5b96-119">![Model icon](../media/model-icon.gif "Model icon") report model icon</span></span>

 <span data-ttu-id="a5b96-120">ícone de ![recurso genérico](../media/hlp-16file.gif "ícone de recurso genérico") ícone de recurso genérico</span><span class="sxs-lookup"><span data-stu-id="a5b96-120">![generic resource icon](../media/hlp-16file.gif "generic resource icon") generic resource icon</span></span>

 <span data-ttu-id="a5b96-121">Ao ser carregado, o arquivo sempre é colocado na pasta que está selecionada atualmente.</span><span class="sxs-lookup"><span data-stu-id="a5b96-121">When you upload a file, it is always placed in the folder that is currently selected.</span></span> <span data-ttu-id="a5b96-122">Você pode navegar até a pasta na qual deseja incluir o item primeiro ou carregar um arquivo e, em seguida, movê-lo para um local final posteriormente.</span><span class="sxs-lookup"><span data-stu-id="a5b96-122">You can navigate to the folder that you want to contain the item first, or you can upload a file and then move it to a final location later.</span></span>

 <span data-ttu-id="a5b96-123">Para carregar um arquivo, use o Gerente de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="a5b96-123">To upload a file, use Report Manager.</span></span> <span data-ttu-id="a5b96-124">O carregamento de arquivos em um servidor de relatório depende das tarefas que fazem parte de sua atribuição de função.</span><span class="sxs-lookup"><span data-stu-id="a5b96-124">Whether you can upload files to a report server depends on tasks that are part of your role assignment.</span></span> <span data-ttu-id="a5b96-125">Se a segurança padrão for usada, os administradores locais poderão adicionar itens a um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="a5b96-125">If you are using default security, local administrators can add items to a report server.</span></span> <span data-ttu-id="a5b96-126">Se Meus Relatórios estiver habilitado, qualquer usuário que tiver uma pasta Meus Relatórios terá permissão para carregar itens nessa pasta.</span><span class="sxs-lookup"><span data-stu-id="a5b96-126">If My Reports is enabled, any user who has a My Reports folder has permission to upload items to that folder.</span></span> <span data-ttu-id="a5b96-127">Se atribuições de função personalizadas forem utilizadas, a atribuição de função deve incluir tarefas que ofereçam suporte para o gerenciamento de pastas.</span><span class="sxs-lookup"><span data-stu-id="a5b96-127">If you use custom role assignments, the role assignment must include tasks that support folder management.</span></span>

|<span data-ttu-id="a5b96-128">Para fazer isto</span><span class="sxs-lookup"><span data-stu-id="a5b96-128">To do this</span></span>|<span data-ttu-id="a5b96-129">Inclua estas tarefas</span><span class="sxs-lookup"><span data-stu-id="a5b96-129">Include these tasks</span></span>|
|----------------|-------------------------|
|<span data-ttu-id="a5b96-130">Carregar um arquivo .rdl em uma pasta</span><span class="sxs-lookup"><span data-stu-id="a5b96-130">Upload an .rdl file to a folder</span></span>|<span data-ttu-id="a5b96-131">Gerenciar relatórios</span><span class="sxs-lookup"><span data-stu-id="a5b96-131">Manage reports</span></span>|
|<span data-ttu-id="a5b96-132">Carregar qualquer arquivo como um objeto binário</span><span class="sxs-lookup"><span data-stu-id="a5b96-132">Upload any file as a binary object</span></span>|<span data-ttu-id="a5b96-133">Gerenciar recursos</span><span class="sxs-lookup"><span data-stu-id="a5b96-133">Manage resources</span></span>|
|<span data-ttu-id="a5b96-134">Exibir o conteúdo de uma pasta</span><span class="sxs-lookup"><span data-stu-id="a5b96-134">View the contents of a folder</span></span>|<span data-ttu-id="a5b96-135">Exibir recursos, exibir relatórios</span><span class="sxs-lookup"><span data-stu-id="a5b96-135">View resources, View reports</span></span>|

## <a name="see-also"></a><span data-ttu-id="a5b96-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a5b96-136">See Also</span></span>
 <span data-ttu-id="a5b96-137">[Report Manager &#40;modo nativo do SSRS&#41;].. /report-manager-ssrs-native-mode.md) [conceder permissões em](../security/granting-permissions-on-a-native-mode-report-server.md) [tarefas e permissões](../security/tasks-and-permissions.md) do servidor de relatório no modo nativo [carregar um arquivo ou relatório &#40;Report Manager&#41;](../reports/upload-a-file-or-report-report-manager.md)</span><span class="sxs-lookup"><span data-stu-id="a5b96-137">[Report Manager  &#40;SSRS Native Mode&#41;]../report-manager-ssrs-native-mode.md) [Granting Permissions on a Native Mode Report Server](../security/granting-permissions-on-a-native-mode-report-server.md) [Tasks and Permissions](../security/tasks-and-permissions.md) [Upload a File or Report &#40;Report Manager&#41;](../reports/upload-a-file-or-report-report-manager.md)</span></span>


