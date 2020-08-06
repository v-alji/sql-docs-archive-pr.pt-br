---
title: Caixa de diálogo Alterações Detectadas no Banco de Dados (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.schema.databasechangesdetected
- vdtsql.chm:65543
- vdtsql.chm:65554
ms.assetid: 91f13086-371f-46a2-9f46-804c1415f3ed
author: stevestein
ms.author: sstein
ms.openlocfilehash: 91d58e812b93f207d592d245d094b0fbeddcce72
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680242"
---
# <a name="database-changes-detected-dialog-box-visual-database-tools"></a><span data-ttu-id="5dff8-102">Caixa de diálogo Alterações Detectadas no Banco de Dados (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="5dff8-102">Database Changes Detected Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="5dff8-103">Essa caixa de diálogo aparece quando se tenta salvar um diagrama de banco de dados ou tabelas selecionadas, porém, alguns objetos de banco de dados que serão afetados pela ação de gravação encontram-se desatualizados em relação ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="5dff8-103">This dialog appears if you attempt to save a database diagram or selected tables but some of the database objects that will be affected by the save action are out of date with the database.</span></span> <span data-ttu-id="5dff8-104">Aceitar as alterações mostradas nessa caixa de diálogo atualizará o banco de dados, que poderá corresponder ao diagrama e substituir alterações de outros usuários.</span><span class="sxs-lookup"><span data-stu-id="5dff8-104">Accepting the changes shown in this dialog box updates the database to match your diagram and overwrites other users' changes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5dff8-105">Embora não seja possível desfazer alterações feitas em uma tabela ou diagrama de banco de dados, as alterações não são salvas no banco de dados até que a tabela ou diagrama sejam salvos.</span><span class="sxs-lookup"><span data-stu-id="5dff8-105">Although you cannot undo changes made to a table or database diagram, the changes are not saved to the database until you save the table or diagram.</span></span> <span data-ttu-id="5dff8-106">Você pode descartar qualquer alteração não salva, selecionando **Não** e fechando todos os diagramas abertos sem os salvar.</span><span class="sxs-lookup"><span data-stu-id="5dff8-106">You can discard any unsaved changes by choosing **No** and closing all open diagrams without saving them.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5dff8-107">Opções</span><span class="sxs-lookup"><span data-stu-id="5dff8-107">Options</span></span>  
 <span data-ttu-id="5dff8-108">**Aviso sobre detecção de diferença**</span><span class="sxs-lookup"><span data-stu-id="5dff8-108">**Warn about difference detection**</span></span>  
 <span data-ttu-id="5dff8-109">Determine se essa caixa de diálogo deverá aparecer na próxima vez você tentar salvar um diagrama de banco de dados ou selecionar tabelas.</span><span class="sxs-lookup"><span data-stu-id="5dff8-109">Specify whether this dialog box appears the next time you attempt to save a database diagram or selected tables.</span></span> <span data-ttu-id="5dff8-110">Marcar significa que a caixa de diálogo continuará a aparecer toda vez que você salvar um diagrama ou tabela desatualizados com relação ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="5dff8-110">Checked means that the dialog box continues to appear each time you save a diagram or table that is out of date with the database.</span></span> <span data-ttu-id="5dff8-111">Desmarcar significa que a caixa de diálogo não será exibida.</span><span class="sxs-lookup"><span data-stu-id="5dff8-111">Unchecked means that the dialog box does not appear.</span></span> <span data-ttu-id="5dff8-112">Por padrão, essa caixa é marcada.</span><span class="sxs-lookup"><span data-stu-id="5dff8-112">By default, this box is checked.</span></span> <span data-ttu-id="5dff8-113">Se desmarcar a opção, você poderá marcá-la novamente na caixa de diálogo **Opções** .</span><span class="sxs-lookup"><span data-stu-id="5dff8-113">If you uncheck this option, you can recheck it in the **Options** dialog box.</span></span>  
  
 <span data-ttu-id="5dff8-114">**Sim**</span><span class="sxs-lookup"><span data-stu-id="5dff8-114">**Yes**</span></span>  
 <span data-ttu-id="5dff8-115">Atualiza o banco de dados com todas as alterações mostradas na lista.</span><span class="sxs-lookup"><span data-stu-id="5dff8-115">Update the database with all the changes shown in the list.</span></span>  
  
 <span data-ttu-id="5dff8-116">**Não**</span><span class="sxs-lookup"><span data-stu-id="5dff8-116">**No**</span></span>  
 <span data-ttu-id="5dff8-117">Cancela a ação de salvar.</span><span class="sxs-lookup"><span data-stu-id="5dff8-117">Cancel the save action.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5dff8-118">Para atualizar o diagrama de modo que ele corresponda ao banco de dados, feche-o sem salvar as alterações; clique com o botão direito do mouse no diagrama, no Explorador de servidores, e clique em Atualizar. Em seguida, abra novamente o diagrama.</span><span class="sxs-lookup"><span data-stu-id="5dff8-118">To refresh your diagram to match the database, close it without saving changes, right-click the diagram in Server Explorer and click Refresh, and then reopen the diagram.</span></span>  
  
 <span data-ttu-id="5dff8-119">**Salvar Arquivo de Texto**</span><span class="sxs-lookup"><span data-stu-id="5dff8-119">**Save Text File**</span></span>  
 <span data-ttu-id="5dff8-120">Exibe a caixa de diálogo **Salvar como** , permitindo especificar um local para um arquivo de texto contendo a lista de alterações do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="5dff8-120">Display the **Save As** dialog box, letting you specify a location for a text file containing a list of the database changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dff8-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5dff8-121">See Also</span></span>  
 <span data-ttu-id="5dff8-122">[Reconciliar um diagrama de banco de dados com um banco de dados modificado &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="5dff8-122">[Reconcile a Database Diagram with a Modified Database &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="5dff8-123">Ambientes multiusuários &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="5dff8-123">Multiuser Environments &#40;Visual Database Tools&#41;</span></span>](multiuser-environments-visual-database-tools.md)  
  
  
