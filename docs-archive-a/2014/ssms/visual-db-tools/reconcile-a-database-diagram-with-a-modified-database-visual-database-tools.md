---
title: Reconciliar um diagrama de banco de dados com um banco de dados modificado (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- updating diagram to match database
- reconciling database diagrams
- diagrams [SQL Server], reconciling changes
- updating database to match diagram
- database diagrams [SQL Server], reconciling changes
ms.assetid: eda8dea2-eedd-43a7-85aa-92bd97783b5f
author: stevestein
ms.author: sstein
ms.openlocfilehash: e5e5127ab613a6f791919a98899e40caa2ddac20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679604"
---
# <a name="reconcile-a-database-diagram-with-a-modified-database-visual-database-tools"></a><span data-ttu-id="51105-102">Reconciliar um diagrama de banco de dados com um banco de dados modificado (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="51105-102">Reconcile a Database Diagram with a Modified Database (Visual Database Tools)</span></span>
  <span data-ttu-id="51105-103">Você salva seu diagrama de banco de dados, quando estiver pronto para atualizar o banco de dados, de forma que ele corresponda ao seu diagrama.</span><span class="sxs-lookup"><span data-stu-id="51105-103">You save your database diagram when you are ready to update the database to match your diagram.</span></span> <span data-ttu-id="51105-104">Porém, se outros usuários tiverem atualizado o banco de dados desde que você abriu seu diagrama, essas alterações podem afetar seu diagrama e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="51105-104">However, if other users have updated the database since you opened your diagram, their changes might affect your diagram and vice versa.</span></span>  
  
 <span data-ttu-id="51105-105">Salvar seu diagrama reconciliará o banco de dados com seu diagrama, substituindo as alterações de outros usuários para que o banco de dados corresponda ao seu diagrama.</span><span class="sxs-lookup"><span data-stu-id="51105-105">Saving your diagram will reconcile the database with your diagram by overwriting other users' changes so that the database will match your diagram.</span></span>  
  
### <a name="to-update-a-database-to-match-your-diagram"></a><span data-ttu-id="51105-106">Para atualizar um banco de dados para que ele corresponda ao seu diagrama</span><span class="sxs-lookup"><span data-stu-id="51105-106">To update a database to match your diagram</span></span>  
  
1.  <span data-ttu-id="51105-107">Salve seu diagrama de banco de dados</span><span class="sxs-lookup"><span data-stu-id="51105-107">Save your database diagram.</span></span>  
  
     <span data-ttu-id="51105-108">Se você não salvou seu diagrama anteriormente, digite um nome para o diagrama na caixa de diálogo **Salvar Novo Diagrama de Banco de Dados** e escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="51105-108">If you have not previously saved your diagram, type a name for the diagram in the **Save New Database Diagram** dialog box and choose **OK**.</span></span>  
  
2.  <span data-ttu-id="51105-109">A caixa de diálogo **Salvar** lista as tabelas que serão afetadas quando você salvar seu diagrama.</span><span class="sxs-lookup"><span data-stu-id="51105-109">The **Save** dialog box lists the tables that will be affected when you save your diagram.</span></span> <span data-ttu-id="51105-110">Escolha **Sim** para continuar.</span><span class="sxs-lookup"><span data-stu-id="51105-110">Choose **Yes** to continue.</span></span>  
  
3.  <span data-ttu-id="51105-111">A caixa de diálogo **Alterações de Banco de Dados Detectadas** lista os objetos que foram modificados e serão alterados para corresponder a seu diagrama.</span><span class="sxs-lookup"><span data-stu-id="51105-111">The **Database Changes Detected** dialog box lists the objects that were modified and will be changed to match your diagram.</span></span> <span data-ttu-id="51105-112">Escolha **Sim** para salvar o diagrama e aceitar a lista de alterações.</span><span class="sxs-lookup"><span data-stu-id="51105-112">Choose **Yes** to save the diagram and accept the list of changes.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="51105-113">Se seu diagrama contiver tabelas e colunas que foram excluídas no banco de dados, só suas definições serão recriadas no banco de dados quando você salvar seu diagrama.</span><span class="sxs-lookup"><span data-stu-id="51105-113">If your diagram contains tables and columns that were deleted in the database, only their definitions are recreated in the database when you save your diagram.</span></span> <span data-ttu-id="51105-114">Este processo não restaura quaisquer dados que existiam nestes objetos antes de sua exclusão.</span><span class="sxs-lookup"><span data-stu-id="51105-114">This process does not restore any data that existed in these objects before their deletion.</span></span>  
  
### <a name="to-update-your-diagram-to-match-a-modified-database"></a><span data-ttu-id="51105-115">Para atualizar seu diagrama para que ele corresponda a um banco de dados modificado</span><span class="sxs-lookup"><span data-stu-id="51105-115">To update your diagram to match a modified database</span></span>  
  
1.  <span data-ttu-id="51105-116">Feche seu diagrama sem salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="51105-116">Close your diagram without saving changes.</span></span>  
  
2.  <span data-ttu-id="51105-117">Clique com o botão direito no diagrama no Pesquisador de Objetos</span><span class="sxs-lookup"><span data-stu-id="51105-117">Right-click the diagram in Object Explorer.</span></span>  
  
3.  <span data-ttu-id="51105-118">No menu de atalho, clique em **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="51105-118">From the shortcut menu click **Refresh**.</span></span>  
  
4.  <span data-ttu-id="51105-119">Reabra o diagrama.</span><span class="sxs-lookup"><span data-stu-id="51105-119">Reopen the diagram.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51105-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="51105-120">See Also</span></span>  
 [<span data-ttu-id="51105-121">Trabalhar com diagramas de banco de dados &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="51105-121">Work with Database Diagrams &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
