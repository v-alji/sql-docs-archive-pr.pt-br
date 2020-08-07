---
title: Modificar restrições exclusivas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- modifying constraints
- UNIQUE constraints [SQL Server], modifying
- constraints [SQL Server], modifying
- constraints [SQL Server], unique
ms.assetid: fddbdc9e-958b-4614-8e88-6ca205d64a4e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 74b044202f7e8e9bc762f025833cf2d0ff84c4c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584075"
---
# <a name="modify-unique-constraints"></a><span data-ttu-id="f2c36-102">Modificar restrições exclusivas</span><span class="sxs-lookup"><span data-stu-id="f2c36-102">Modify Unique Constraints</span></span>
  <span data-ttu-id="f2c36-103">Você pode modificar uma restrição exclusiva no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2c36-103">You can modify a unique constraint in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="f2c36-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="f2c36-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f2c36-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="f2c36-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f2c36-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="f2c36-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f2c36-107">**Para modificar uma restrição exclusiva usando:**</span><span class="sxs-lookup"><span data-stu-id="f2c36-107">**To modify a unique constraint using:**</span></span>  
  
     [<span data-ttu-id="f2c36-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f2c36-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f2c36-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f2c36-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f2c36-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="f2c36-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f2c36-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="f2c36-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f2c36-112">Permissões</span><span class="sxs-lookup"><span data-stu-id="f2c36-112">Permissions</span></span>  
 <span data-ttu-id="f2c36-113">Exige a permissão ALTER na tabela.</span><span class="sxs-lookup"><span data-stu-id="f2c36-113">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f2c36-114">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f2c36-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-unique-constraint"></a><span data-ttu-id="f2c36-115">Para modificar uma restrição exclusiva</span><span class="sxs-lookup"><span data-stu-id="f2c36-115">To modify a unique constraint</span></span>  
  
1.  <span data-ttu-id="f2c36-116">No **Pesquisador de Objetos**, clique com o botão direito do mouse na tabela que contém restrição exclusiva e selecione **Design**.</span><span class="sxs-lookup"><span data-stu-id="f2c36-116">In the **Object Explorer**, right-click the table containing the unique constraint and select **Design**.</span></span>  
  
2.  <span data-ttu-id="f2c36-117">No menu **Designer de Tabela**, clique em **Índices/Chaves...** .</span><span class="sxs-lookup"><span data-stu-id="f2c36-117">On the **Table Designer** menu, click **Indexes/Keys...**.</span></span>  
  
3.  <span data-ttu-id="f2c36-118">Na caixa de diálogo **Índices/Chaves** , selecione **Índice ou Chave Exclusiva/Primária Selecionada**e selecione a restrição que deseja editar.</span><span class="sxs-lookup"><span data-stu-id="f2c36-118">In the **Indexes/Keys** dialog box, under **Selected Primary/Unique Key or Index**, select the constraint you wish to edit.</span></span>  
  
4.  <span data-ttu-id="f2c36-119">Complete uma ação da seguinte tabela:</span><span class="sxs-lookup"><span data-stu-id="f2c36-119">Complete an action from the following table:</span></span>  
  
    |<span data-ttu-id="f2c36-120">Para</span><span class="sxs-lookup"><span data-stu-id="f2c36-120">To</span></span>|<span data-ttu-id="f2c36-121">Siga estas etapas</span><span class="sxs-lookup"><span data-stu-id="f2c36-121">Follow these steps</span></span>|  
    |--------|------------------------|  
    |<span data-ttu-id="f2c36-122">Alterar as colunas às quais a restrição está associada</span><span class="sxs-lookup"><span data-stu-id="f2c36-122">Change the columns that the constraint is associated with</span></span>|<span data-ttu-id="f2c36-123">1) Na grade, em **(Geral)** , clique em **Colunas** e nas reticências **(…)** à direita da propriedade.</span><span class="sxs-lookup"><span data-stu-id="f2c36-123">1) In the grid under **(General)**, click **Columns** and then click the ellipses **(...)** to the right of the property.</span></span><br /><br /> <span data-ttu-id="f2c36-124">2) Na caixa de diálogo **Colunas de Índice** , especifique a nova coluna, a ordem de classificação ou ambas para o índice.</span><span class="sxs-lookup"><span data-stu-id="f2c36-124">2) In the **Index Columns** dialog box, specify the new column or sort order or both for the index.</span></span>|  
    |<span data-ttu-id="f2c36-125">Renomear a restrição</span><span class="sxs-lookup"><span data-stu-id="f2c36-125">Rename the constraint</span></span>|<span data-ttu-id="f2c36-126">Na grade, em **Identidade**, digite um novo nome na caixa **Nome** .</span><span class="sxs-lookup"><span data-stu-id="f2c36-126">In the grid under **Identity**, type a new name in the **Name** box.</span></span> <span data-ttu-id="f2c36-127">Verifique se seu novo nome não duplica um nome na lista **Índice ou Chave Exclusiva/Primária Selecionada** .</span><span class="sxs-lookup"><span data-stu-id="f2c36-127">Make sure that your new name does not duplicate a name in the **Selected Primary/Unique Key or Index** list.</span></span>|  
    |<span data-ttu-id="f2c36-128">Definir a opção clustered</span><span class="sxs-lookup"><span data-stu-id="f2c36-128">Set the clustered option</span></span>|<span data-ttu-id="f2c36-129">Na grade, em **Designer de Tabela**, selecione **Criar como Clusterizado** e, na lista suspensa, escolha Sim para criar um índice clusterizado e Não para criar um não clusterizado.</span><span class="sxs-lookup"><span data-stu-id="f2c36-129">In the grid under **Table Designer**, select **Create As Clustered** and from the dropdown choose Yes to create a clustered index and No to create a nonclustered one.</span></span> <span data-ttu-id="f2c36-130">Só pode existir um índice clusterizado por tabela.</span><span class="sxs-lookup"><span data-stu-id="f2c36-130">Only one clustered index can exist per table.</span></span> <span data-ttu-id="f2c36-131">Se já houver um índice clusterizado nessa tabela, você deverá desmarcar essa configuração no índice original.</span><span class="sxs-lookup"><span data-stu-id="f2c36-131">If a clustered index already exists in this table, you must clear this setting on the original index.</span></span>|  
    |<span data-ttu-id="f2c36-132">Definir um fator de preenchimento</span><span class="sxs-lookup"><span data-stu-id="f2c36-132">Define a fill factor</span></span>|<span data-ttu-id="f2c36-133">Na grade, em **Designer de Tabela**, expanda a categoria **Especificação de Preenchimento** e digite um inteiro de 0 a 100 na caixa **Fator de Preenchimento** .</span><span class="sxs-lookup"><span data-stu-id="f2c36-133">In the grid under **Table Designer**, expand the **Fill Specification** category and type an integer from 0 to 100 in the **Fill Factor** box.</span></span>|  
  
5.  <span data-ttu-id="f2c36-134">No menu **Arquivo**, clique em **Salvar**_nome da tabela_.</span><span class="sxs-lookup"><span data-stu-id="f2c36-134">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="to-modify-a-unique-constraint"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f2c36-135">**Para modificar uma restrição exclusiva**</span><span class="sxs-lookup"><span data-stu-id="f2c36-135">**To modify a unique constraint**</span></span>  
  
 <span data-ttu-id="f2c36-136">Para modificar a restrição UNIQUE usando o Transact-SQL, exclua primeiramente a restrição UNIQUE existente e, em seguida, recrie-a com a nova definição.</span><span class="sxs-lookup"><span data-stu-id="f2c36-136">To modify a UNIQUE constraint using Transact-SQL, you must first delete the existing UNIQUE constraint and then re-create it with the new definition.</span></span> <span data-ttu-id="f2c36-137">Para obter mais informações, consulte [Delete Unique Constraints](delete-unique-constraints.md) e [Create Unique Constraints](create-unique-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="f2c36-137">For more information, see [Delete Unique Constraints](delete-unique-constraints.md) and [Create Unique Constraints](create-unique-constraints.md).</span></span>  
  
###  <a name="TsqlExample"></a>  
