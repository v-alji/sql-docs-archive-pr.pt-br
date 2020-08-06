---
title: Editar arquivos com check-in | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- modifying checked-in files
- checking in files
ms.assetid: 560cd19f-ab22-4273-b00c-149993a630e6
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: e2dbe1aad203dfdc83e438d5b7f4ed19c15038c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681095"
---
# <a name="edit-checked-in-files"></a><span data-ttu-id="33ccc-102">Editar arquivos com check-in</span><span class="sxs-lookup"><span data-stu-id="33ccc-102">Edit Checked-In Files</span></span>
  <span data-ttu-id="33ccc-103">Você normalmente deve fazer o check-out de arquivos com controle do código-fonte antes de poder editá-los.</span><span class="sxs-lookup"><span data-stu-id="33ccc-103">You typically must check out source-controlled files before you can edit them.</span></span> <span data-ttu-id="33ccc-104">No entanto, você pode configurar o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para que você possa modificar os arquivos que não fez check-out. Ao fazer isso, suas alterações são mantidas na memória até que você salve os arquivos.</span><span class="sxs-lookup"><span data-stu-id="33ccc-104">However, you can configure [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] so that you can modify files you have not checked out. When doing so, your changes are held in memory until you save the files.</span></span> <span data-ttu-id="33ccc-105">Você será solicitado a fazer check–out do arquivo no controle do código-fonte.</span><span class="sxs-lookup"><span data-stu-id="33ccc-105">You will then be prompted to check out the file from source control.</span></span>  
  
 <span data-ttu-id="33ccc-106">Se você trabalhar em equipe, não se recomenda permitir o check-in de arquivos a menos que seu provedor de controle do código-fonte ofereça suporte a check-outs de versão local e de servidor.</span><span class="sxs-lookup"><span data-stu-id="33ccc-106">If you work on a team, allowing checked-in files to be edited is not recommended unless your source control provider supports both local version and server version checkouts.</span></span> <span data-ttu-id="33ccc-107">A maioria dos provedores não dá suporte a check-outs de versões locais.</span><span class="sxs-lookup"><span data-stu-id="33ccc-107">Most providers do not support local version checkouts.</span></span> <span data-ttu-id="33ccc-108">Se seu provedor não oferecer suporte a check-outs de versões locais e você editar um arquivo com check-in, será necessário mesclar as versões da memória e do servidor manualmente para que o arquivo possa ser submetido a check-in.</span><span class="sxs-lookup"><span data-stu-id="33ccc-108">If your provider does not support local version checkouts and you edit a checked-in file, you have to merge the in-memory and server versions manually before the file can be checked in.</span></span> <span data-ttu-id="33ccc-109">Não há suporte para mesclagens automáticas e auxiliadas por provedor nesta situação.</span><span class="sxs-lookup"><span data-stu-id="33ccc-109">Automatic and provider-assisted merges are unsupported in this situation.</span></span>  
  
### <a name="to-edit-checked-in-files"></a><span data-ttu-id="33ccc-110">Para editar arquivos com check-in</span><span class="sxs-lookup"><span data-stu-id="33ccc-110">To edit checked-in files</span></span>  
  
1.  <span data-ttu-id="33ccc-111">No menu **Ferramentas** , clique em **Opções**.</span><span class="sxs-lookup"><span data-stu-id="33ccc-111">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="33ccc-112">Na caixa de diálogo **Opções** , expanda a pasta **Controle do Código-Fonte**e clique em **Ambiente**.</span><span class="sxs-lookup"><span data-stu-id="33ccc-112">In the **Options** dialog box, expand the **Source Contro**l folder, and then click **Environment**.</span></span>  
  
3.  <span data-ttu-id="33ccc-113">Clique **Permitir edição de itens com check-in**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="33ccc-113">Click **Allow checked-in items to be edited**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33ccc-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="33ccc-114">See Also</span></span>  
 <span data-ttu-id="33ccc-115">[Gerenciar Check-ins](../../2014/database-engine/manage-checkins.md) </span><span class="sxs-lookup"><span data-stu-id="33ccc-115">[Manage Checkins](../../2014/database-engine/manage-checkins.md) </span></span>  
 [<span data-ttu-id="33ccc-116">Gerenciar check-outs</span><span class="sxs-lookup"><span data-stu-id="33ccc-116">Manage Checkouts</span></span>](../../2014/database-engine/manage-checkouts.md)  
  
  
