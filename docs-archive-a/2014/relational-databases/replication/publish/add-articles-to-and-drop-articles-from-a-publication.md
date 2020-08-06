---
title: Adicionar e remover artigos de uma publicação (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- articles [SQL Server replication], dropping
- deleting articles
- dropping articles
- adding articles
- articles [SQL Server replication], adding
ms.assetid: d5a3e536-62d2-4473-a178-877ba52f7d7f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f7af1cac1f3ee8ecc9cb79632f8a4ef1e66ec82f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583514"
---
# <a name="add-articles-to-and-drop-articles-from-a-publication-sql-server-management-studio"></a><span data-ttu-id="fa927-102">Adicionar e descartar artigos em uma publicação (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="fa927-102">Add Articles to and Drop Articles from a Publication (SQL Server Management Studio)</span></span>
  <span data-ttu-id="fa927-103">Inicialmente, adicione os artigos a uma publicação ao criá-la no Assistente para Nova Publicação.</span><span class="sxs-lookup"><span data-stu-id="fa927-103">Initially add articles to a publication when you create it in the New Publication Wizard.</span></span> <span data-ttu-id="fa927-104">Para obter mais informações sobre como usar esse assistente, consulte [Criar uma publicação](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="fa927-104">For more information about using this wizard, see [Create a Publication](create-a-publication.md).</span></span>  
  
 <span data-ttu-id="fa927-105">Após a criação da publicação, adicione e exclua artigos na página **Artigos** da caixa de diálogo **Propriedades da Publicação – \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="fa927-105">After a publication is created, add and delete articles on the **Articles** page of the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="fa927-106">Para obter mais informações sobre como acessar essa caixa de diálogo, consulte [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="fa927-106">For more information about accessing this dialog box, see [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span> <span data-ttu-id="fa927-107">Para obter informações sobre as considerações para adicionar e remover artigos, consulte [Adicionar e remover artigos de publicações existentes](add-articles-to-and-drop-articles-from-existing-publications.md).</span><span class="sxs-lookup"><span data-stu-id="fa927-107">For information about the considerations for adding and dropping articles, see [Add Articles to and Drop Articles from Existing Publications](add-articles-to-and-drop-articles-from-existing-publications.md).</span></span>  
  
### <a name="to-add-an-article-after-a-publication-is-created"></a><span data-ttu-id="fa927-108">Para adicionar um artigo após a criação de uma publicação</span><span class="sxs-lookup"><span data-stu-id="fa927-108">To add an article after a publication is created</span></span>  
  
1.  <span data-ttu-id="fa927-109">Na página **Artigos** da caixa de diálogo **Propriedades da Publicação – \<Publication>** , desmarque a caixa de seleção **Mostrar somente os objetos marcados na lista**.</span><span class="sxs-lookup"><span data-stu-id="fa927-109">On the **Articles** page of the **Publication Properties - \<Publication>** dialog box, clear the **Show only checked objects in the list** check box.</span></span> <span data-ttu-id="fa927-110">Isso permitirá ver os objetos não publicados, no banco de dados de publicação.</span><span class="sxs-lookup"><span data-stu-id="fa927-110">This allows you to see the unpublished objects in the publication database.</span></span>  
  
2.  <span data-ttu-id="fa927-111">Marque a caixa de seleção próxima a cada artigo que você quer adicionar.</span><span class="sxs-lookup"><span data-stu-id="fa927-111">Select the check box next to each article you want to add.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-delete-an-article"></a><span data-ttu-id="fa927-112">Para excluir um artigo</span><span class="sxs-lookup"><span data-stu-id="fa927-112">To delete an article</span></span>  
  
1.  <span data-ttu-id="fa927-113">Na página **Artigos** da caixa de diálogo **Propriedades da Publicação – \<Publication>** , desmarque a caixa de seleção ao lado de cada artigo que deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="fa927-113">On the **Articles** page of the **Publication Properties - \<Publication>** dialog box, clear the check box next to each article you want to delete.</span></span>  
  
2.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fa927-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fa927-114">See Also</span></span>  
 <span data-ttu-id="fa927-115">[Define an Article](define-an-article.md) </span><span class="sxs-lookup"><span data-stu-id="fa927-115">[Define an Article](define-an-article.md) </span></span>  
 [<span data-ttu-id="fa927-116">Publicar dados e objetos de banco de dados</span><span class="sxs-lookup"><span data-stu-id="fa927-116">Publish Data and Database Objects</span></span>](publish-data-and-database-objects.md)  
  
  
