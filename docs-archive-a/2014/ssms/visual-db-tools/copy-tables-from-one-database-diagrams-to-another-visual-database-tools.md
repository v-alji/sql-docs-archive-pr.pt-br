---
title: Copiar tabelas de diagramas de um banco de dados para outro (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- copying tables
- duplicating tables
ms.assetid: 155a4f09-9321-4887-a7d4-aa2ce6b51277
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7e90c8f324e80f7c59674def06a77e93a5bf0cb1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678501"
---
# <a name="copy-tables-from-one-database-diagrams-to-another-visual-database-tools"></a><span data-ttu-id="8662d-102">Copiar tabelas de diagramas de um banco de dados para outro (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="8662d-102">Copy Tables from One Database Diagrams to Another (Visual Database Tools)</span></span>
  <span data-ttu-id="8662d-103">Você pode copiar uma tabela de um diagrama de banco de dados para outro no mesmo banco de dados.</span><span class="sxs-lookup"><span data-stu-id="8662d-103">You can copy a table from one database diagram to another in the same database.</span></span>  
  
 <span data-ttu-id="8662d-104">Copiando uma tabela de um diagrama de banco de dados para outro diagrama adiciona uma referência à tabela no segundo diagrama.</span><span class="sxs-lookup"><span data-stu-id="8662d-104">Copying a table from one database diagram to another diagram adds a reference to the table in the second diagram.</span></span> <span data-ttu-id="8662d-105">A tabela não é duplicada no seu banco de dados.</span><span class="sxs-lookup"><span data-stu-id="8662d-105">The table is not duplicated in your database.</span></span> <span data-ttu-id="8662d-106">Por exemplo, se você copiar a tabela `authors` de um diagrama de banco de dados para outro, cada diagrama referencia a mesma tabela `authors` no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="8662d-106">For example, if you copy the `authors` table from one database diagram to another, each diagram references the same `authors` table in the database.</span></span>  
  
### <a name="to-copy-a-table-from-another-database-diagram"></a><span data-ttu-id="8662d-107">Para copiar uma tabela de outro diagrama de banco de dados</span><span class="sxs-lookup"><span data-stu-id="8662d-107">To copy a table from another database diagram</span></span>  
  
1.  <span data-ttu-id="8662d-108">Verifique se você está conectado ao banco de dados da tabela a ser copiada.</span><span class="sxs-lookup"><span data-stu-id="8662d-108">Make sure you are connected to the database whose table you want to copy.</span></span>  
  
2.  <span data-ttu-id="8662d-109">Abra os diagramas de origem e de destino do banco de dados e dentro do diagrama de origem, selecione a tabela que você deseja copiar no diagrama de destino.</span><span class="sxs-lookup"><span data-stu-id="8662d-109">Open the source and target database diagrams and within the source diagram, select the table that you want to copy to the target diagram.</span></span>  
  
3.  <span data-ttu-id="8662d-110">Clique no botão **Copiar** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="8662d-110">Click the **Copy** button on the toolbar.</span></span> <span data-ttu-id="8662d-111">Essa ação coloca a definição da tabela selecionada na Área de Transferência.</span><span class="sxs-lookup"><span data-stu-id="8662d-111">This action places the selected table definition on the Clipboard.</span></span>  
  
4.  <span data-ttu-id="8662d-112">Alterne para o diagrama de destino.</span><span class="sxs-lookup"><span data-stu-id="8662d-112">Switch to the target diagram.</span></span> <span data-ttu-id="8662d-113">Esse diagrama deve estar no mesmo banco de dados do diagrama de origem.</span><span class="sxs-lookup"><span data-stu-id="8662d-113">This diagram must be in the same database as the source diagram.</span></span>  
  
5.  <span data-ttu-id="8662d-114">Clique no botão **Colar** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="8662d-114">Click the **Paste** button on the toolbar.</span></span> <span data-ttu-id="8662d-115">O conteúdo da Área de Transferência aparece no novo local e permanece realçado até que você clique em outro lugar.</span><span class="sxs-lookup"><span data-stu-id="8662d-115">The Clipboard contents appear at the new location and remain highlighted until you click elsewhere.</span></span> <span data-ttu-id="8662d-116">Se existir relações entre as tabelas selecionadas e outras tabelas no diagrama de destino, linhas de relação serão desenhadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8662d-116">If relationships exist between the selected tables and other tables in the target diagram, relationship lines are automatically drawn.</span></span>  
  
 <span data-ttu-id="8662d-117">Quando você edita a tabela em qualquer diagrama, suas alterações são refletidas em ambos os diagramas.</span><span class="sxs-lookup"><span data-stu-id="8662d-117">When you edit the table in either diagram, your changes are reflected in both diagrams.</span></span> <span data-ttu-id="8662d-118">Da mesma forma, quando você salva a tabela em qualquer diagrama, a tabela não é mais considerada "modificada" em qualquer diagrama.</span><span class="sxs-lookup"><span data-stu-id="8662d-118">Similarly, once you save the table in either diagram, the table is no longer considered "modified" in either diagram.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8662d-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8662d-119">See Also</span></span>  
 <span data-ttu-id="8662d-120">[Trabalhar com diagramas de banco de dados &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="8662d-120">[Work with Database Diagrams &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="8662d-121">Adicionar tabelas a diagramas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="8662d-121">Add Tables to Diagrams &#40;Visual Database Tools&#41;</span></span>](add-tables-to-diagrams-visual-database-tools.md)  
  
  
