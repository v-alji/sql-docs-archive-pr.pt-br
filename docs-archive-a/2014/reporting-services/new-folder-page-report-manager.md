---
title: Página nova pasta (Report Manager) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9212fc68-f0a6-4f79-83c1-84baf4d1957e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 27c6a82c4911ba42215d4ab7dcafd666ddce5d54
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576244"
---
# <a name="new-folder-page-report-manager"></a><span data-ttu-id="8e5e7-102">Página Nova Pasta (Gerenciador de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="8e5e7-102">New Folder Page (Report Manager)</span></span>
  <span data-ttu-id="8e5e7-103">Use a página Nova Pasta para criar uma pasta nova na hierarquia de pasta do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-103">Use the New Folder page to create a new folder in the report server folder hierarchy.</span></span> <span data-ttu-id="8e5e7-104">A pasta que você cria é uma pasta virtual que é armazenada em um banco de dados do servidor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-104">The folder that you create is a virtual folder that is stored in a report server database.</span></span> <span data-ttu-id="8e5e7-105">A pasta não é criada no sistema de arquivos do seu computador.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-105">The folder is not created in the file system of your computer.</span></span>  
  
 <span data-ttu-id="8e5e7-106">Uma pasta é criada localmente, como uma subpasta da pasta selecionada no momento.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-106">A folder is created in-place, as a subfolder of the folder that is currently selected.</span></span> <span data-ttu-id="8e5e7-107">Antes de criar uma pasta, você deve navegar até o local onde quer criar a pasta.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-107">Before creating a folder, you should navigate to the location where you want to create the folder.</span></span>  
  
 <span data-ttu-id="8e5e7-108">Depois de criar uma pasta, você pode modificar seu nome e sua descrição na página Propriedades gerais da pasta.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-108">After you create a folder, you can modify its name and description through the General properties page of the folder.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="8e5e7-109">Navegação</span><span class="sxs-lookup"><span data-stu-id="8e5e7-109">Navigation</span></span>  
 <span data-ttu-id="8e5e7-110">Use o procedimento a seguir para navegar para este local na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-110">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-new-folder-page"></a><span data-ttu-id="8e5e7-111">Para abrir a página Nova Pasta</span><span class="sxs-lookup"><span data-stu-id="8e5e7-111">To open the New Folder page</span></span>  
  
1.  <span data-ttu-id="8e5e7-112">Abra o Gerenciador de Relatórios e navegue até a pasta na qual você deseja criar uma nova pasta.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-112">Open Report Manager, and navigate to the folder in which you want to create a new folder.</span></span>  
  
2.  <span data-ttu-id="8e5e7-113">Na barra de ferramentas, clique em **Nova Pasta**.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-113">In the toolbar, click **New Folder**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8e5e7-114">Opções</span><span class="sxs-lookup"><span data-stu-id="8e5e7-114">Options</span></span>  
 <span data-ttu-id="8e5e7-115">**Nome**</span><span class="sxs-lookup"><span data-stu-id="8e5e7-115">**Name**</span></span>  
 <span data-ttu-id="8e5e7-116">Especifique o nome da pasta.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-116">Specify the name of the folder.</span></span> <span data-ttu-id="8e5e7-117">Um nome deve conter pelo menos um caractere alfanumérico.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-117">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="8e5e7-118">Também pode conter espaços e certos símbolos.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-118">It can also include spaces and certain symbols.</span></span> <span data-ttu-id="8e5e7-119">Não use os caracteres ; ?</span><span class="sxs-lookup"><span data-stu-id="8e5e7-119">Do not use the characters ; ?</span></span> <span data-ttu-id="8e5e7-120">: \@ & = +, $/\* \< > | "or/ao especificar um nome.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-120">: \@ & = + , $ / \* \< > | " or / when specifying a name.</span></span>  
  
 <span data-ttu-id="8e5e7-121">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="8e5e7-121">**Description**</span></span>  
 <span data-ttu-id="8e5e7-122">Digite uma descrição do conteúdo da pasta.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-122">Type a description of folder contents.</span></span> <span data-ttu-id="8e5e7-123">Essa descrição aparece na página Conteúdo para usuários com permissão para acessar a pasta.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-123">This description appears in the Contents page to users who have permission to access the folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e5e7-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8e5e7-124">See Also</span></span>  
 <span data-ttu-id="8e5e7-125">[Criar, excluir ou modificar uma pasta &#40;Report Manager&#41;](report-server/create-delete-or-modify-a-folder-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="8e5e7-125">[Create, Delete, or Modify a Folder &#40;Report Manager&#41;](report-server/create-delete-or-modify-a-folder-report-manager.md) </span></span>  
 <span data-ttu-id="8e5e7-126">[Página Propriedades gerais, pastas &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-folders-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="8e5e7-126">[General Properties Page, Folders &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-folders-report-manager.md) </span></span>  
 <span data-ttu-id="8e5e7-127">[Gerenciador de Relatórios &#40;Modo Nativo do SSRS&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="8e5e7-127">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="8e5e7-128">[Página de conteúdo &#40;Report Manager&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="8e5e7-128">[Contents Page &#40;Report Manager&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="8e5e7-129">[Ajuda F1 Report Manager](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="8e5e7-129">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 [<span data-ttu-id="8e5e7-130">Página Propriedades gerais, pastas &#40;Report Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="8e5e7-130">General Properties Page, Folders &#40;Report Manager&#41;</span></span>](../../2014/reporting-services/general-properties-page-folders-report-manager.md)  
  
  
