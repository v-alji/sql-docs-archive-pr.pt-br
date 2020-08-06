---
title: Criar relações entre tabelas em um diagrama (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- diagrams [SQL Server], designing
ms.assetid: 28e9630c-dff4-46cc-bb0e-fe77998b6ac2
author: stevestein
ms.author: sstein
ms.openlocfilehash: d7d627a37f84dcb66b2129bb9c7dbc5890ccd46c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684985"
---
# <a name="create-relationships-between-tables-on-a-diagram-visual-database-tools"></a><span data-ttu-id="a4fa4-102">Criar relações entre tabelas em um diagrama (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="a4fa4-102">Create Relationships Between Tables on a Diagram (Visual Database Tools)</span></span>
  <span data-ttu-id="a4fa4-103">Você pode criar relações entre colunas em tabelas diferentes no Designer de Diagrama arrastando colunas entre tabelas.</span><span class="sxs-lookup"><span data-stu-id="a4fa4-103">You can create relationships between columns in different tables in the Diagram Designer by dragging columns between tables.</span></span>  
  
### <a name="to-create-a-relationship-graphically"></a><span data-ttu-id="a4fa4-104">Para criar uma relação graficamente</span><span class="sxs-lookup"><span data-stu-id="a4fa4-104">To create a relationship graphically</span></span>  
  
1.  <span data-ttu-id="a4fa4-105">No Designer de Banco de Dados, clique no seletor de linha de uma ou mais colunas do banco de dados que você quer relacionar a uma coluna em outra tabela.</span><span class="sxs-lookup"><span data-stu-id="a4fa4-105">In Database Designer, click the row selector for one or more database columns that you want to relate to a column in another table.</span></span>  
  
2.  <span data-ttu-id="a4fa4-106">Arraste as colunas selecionadas para a tabela relacionada.</span><span class="sxs-lookup"><span data-stu-id="a4fa4-106">Drag the selected column(s) to the related table.</span></span>  
  
3.  <span data-ttu-id="a4fa4-107">São exibidas duas caixas de diálogo: **Relação de Chaves Estrangeiras** e **Tabelas e Colunas**sendo a última aparecendo no primeiro plano.</span><span class="sxs-lookup"><span data-stu-id="a4fa4-107">Two dialog boxes appear: **Foreign Key Relationship** and **Tables and Columns**, with the latter appearing in the foreground.</span></span>  
  
4.  <span data-ttu-id="a4fa4-108">**Nome da relação** tem um nome fornecido pelo sistema no formato FK_*localtable*_*foreigntable*.</span><span class="sxs-lookup"><span data-stu-id="a4fa4-108">**Relationship name** has a system-provided name in the format FK_*localtable*_*foreigntable*.</span></span> <span data-ttu-id="a4fa4-109">Você pode alterar esse valor.</span><span class="sxs-lookup"><span data-stu-id="a4fa4-109">You may change this value.</span></span>  
  
5.  <span data-ttu-id="a4fa4-110">Verifique se a **Tabela de chaves primárias** especifica a tabela correta.</span><span class="sxs-lookup"><span data-stu-id="a4fa4-110">Verify that **Primary key table** specifies the correct table.</span></span>  
  
6.  <span data-ttu-id="a4fa4-111">A grade lista as colunas locais e as suas colunas estrangeiras correspondentes.</span><span class="sxs-lookup"><span data-stu-id="a4fa4-111">The grid lists the local columns and their matching foreign columns.</span></span> <span data-ttu-id="a4fa4-112">Você pode adicionar ou remover colunas de tabela ou alterar mapeamentos.</span><span class="sxs-lookup"><span data-stu-id="a4fa4-112">You can add or remove table columns or change mappings.</span></span>  
  
7.  <span data-ttu-id="a4fa4-113">Escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="a4fa4-113">Choose **OK**.</span></span>  
  
     <span data-ttu-id="a4fa4-114">A caixa de diálogo **Relação de Chaves Estrangeiras** é exibida.</span><span class="sxs-lookup"><span data-stu-id="a4fa4-114">The **Foreign Key Relationship** dialog box appears.</span></span> <span data-ttu-id="a4fa4-115">**Relação Selecionada** mostra a relação que você criou.</span><span class="sxs-lookup"><span data-stu-id="a4fa4-115">**Selected Relationship** shows the relationship you have created.</span></span>  
  
8.  <span data-ttu-id="a4fa4-116">Altere as propriedades da relação na grade.</span><span class="sxs-lookup"><span data-stu-id="a4fa4-116">Change properties for the relationship in the grid.</span></span>  
  
9. <span data-ttu-id="a4fa4-117">Escolha **OK** para criar a relação.</span><span class="sxs-lookup"><span data-stu-id="a4fa4-117">Choose **OK** to create the relationship.</span></span>  
  
     <span data-ttu-id="a4fa4-118">O Designer de Banco de Dados mostra uma relação entre as colunas que você escolheu.</span><span class="sxs-lookup"><span data-stu-id="a4fa4-118">Database Designer shows a relationship between the columns you chose.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4fa4-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a4fa4-119">See Also</span></span>  
 <span data-ttu-id="a4fa4-120">[Caixa de diálogo tabelas e colunas &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="a4fa4-120">[Tables and Columns Dialog Box &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="a4fa4-121">[Restrições exclusivas e restrições de verificação](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="a4fa4-121">[Unique Constraints and Check Constraints](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span></span>  
 [<span data-ttu-id="a4fa4-122">Trabalhar com tabelas no diagrama de banco de dados &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="a4fa4-122">Work with Tables in Database Diagram &#40;Visual Database Tools&#41;</span></span>](work-with-tables-in-database-diagram-visual-database-tools.md)  
  
  
