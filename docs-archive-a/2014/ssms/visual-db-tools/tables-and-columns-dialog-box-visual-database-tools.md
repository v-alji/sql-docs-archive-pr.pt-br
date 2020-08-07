---
title: Caixa de diálogo Tabelas e Colunas (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.tablesandcolumns
ms.assetid: 8cf27be1-e66d-4735-a428-9ab4b33af4f5
author: stevestein
ms.author: sstein
ms.openlocfilehash: 28e0c52b74413a3a5a4122412c6028b34e974b09
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582243"
---
# <a name="tables-and-columns-dialog-box-visual-database-tools"></a><span data-ttu-id="bff94-102">Caixa de dialogo Tabelas e Colunas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="bff94-102">Tables and Columns Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="bff94-103">Use esta caixa de diálogo para mapear uma chave primária em uma tabela para uma chave estrangeira em outra.</span><span class="sxs-lookup"><span data-stu-id="bff94-103">Use this dialog box to map a primary key in one table to a foreign key in another.</span></span> <span data-ttu-id="bff94-104">Para acessar essa caixa de diálogo, no menu **Designer de Tabela** , clique em **Relações**.</span><span class="sxs-lookup"><span data-stu-id="bff94-104">To access this dialog box, from the **Table Designer** menu, click **Relationships**.</span></span> <span data-ttu-id="bff94-105">Na caixa de diálogo **Relações de Chave Estrangeira**, clique no campo **Especificação das Tabelas e Colunas** e, em seguida, clique nas reticências **(…)** à direita da propriedade.</span><span class="sxs-lookup"><span data-stu-id="bff94-105">In the **Foreign Key Relationships** dialog box, click the **Tables and Columns Specification** field, and then click the ellipses **(...)** to the right of the property.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bff94-106">Se a tabela for publicada para replicação, você precisará fazer alterações no esquema usando a instrução Transact-SQL [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) ou o SMO (SQL Server Management Objects).</span><span class="sxs-lookup"><span data-stu-id="bff94-106">If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="bff94-107">Ao fazer alterações no esquema com o Criador de Tabelas ou com o Criador do Diagrama de Banco de Dados, ele tenta descartar e recriar a tabela.</span><span class="sxs-lookup"><span data-stu-id="bff94-107">When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table.</span></span> <span data-ttu-id="bff94-108">Não é possível descartar objetos publicados, portanto, haverá falha na alteração de esquema.</span><span class="sxs-lookup"><span data-stu-id="bff94-108">You cannot drop published objects, therefore the schema change will fail.</span></span>  
  
## <a name="options"></a><span data-ttu-id="bff94-109">Opções</span><span class="sxs-lookup"><span data-stu-id="bff94-109">Options</span></span>  
 <span data-ttu-id="bff94-110">**Nome da Relação**</span><span class="sxs-lookup"><span data-stu-id="bff94-110">**Relationship name**</span></span>  
 <span data-ttu-id="bff94-111">Mostra o nome da relação.</span><span class="sxs-lookup"><span data-stu-id="bff94-111">Shows the name of the relationship.</span></span>  
  
 <span data-ttu-id="bff94-112">**Tabela de Chaves Primárias**</span><span class="sxs-lookup"><span data-stu-id="bff94-112">**Primary Key Table**</span></span>  
 <span data-ttu-id="bff94-113">Lista as tabelas no banco de dados</span><span class="sxs-lookup"><span data-stu-id="bff94-113">Lists the tables in the database.</span></span> <span data-ttu-id="bff94-114">Selecione a tabela que estará no lado da chave primária da relação.</span><span class="sxs-lookup"><span data-stu-id="bff94-114">Choose the table that will be on the primary-key side of the relationship.</span></span>  
  
 <span data-ttu-id="bff94-115">**Tabela de Chaves Estrangeiras**</span><span class="sxs-lookup"><span data-stu-id="bff94-115">**Foreign Key Table**</span></span>  
 <span data-ttu-id="bff94-116">Mostra a tabela no lado da chave estrangeira da relação.</span><span class="sxs-lookup"><span data-stu-id="bff94-116">Shows the table on the foreign key side of the relationship.</span></span> <span data-ttu-id="bff94-117">Essa é a tabela selecionada atualmente no Designer de Tabela.</span><span class="sxs-lookup"><span data-stu-id="bff94-117">This is the table currently selected in Table Designer.</span></span>  
  
 <span data-ttu-id="bff94-118">**Grade abaixo da Tabela de Chaves Primárias**</span><span class="sxs-lookup"><span data-stu-id="bff94-118">**Grid beneath Primary Key Table**</span></span>  
 <span data-ttu-id="bff94-119">Lista as colunas da tabela selecionada na lista da **Tabela de Chaves Primárias** .</span><span class="sxs-lookup"><span data-stu-id="bff94-119">List the columns of the table selected in the **Primary Key Table** list.</span></span> <span data-ttu-id="bff94-120">Insira as colunas que contribuam para a chave primária daquela tabela.</span><span class="sxs-lookup"><span data-stu-id="bff94-120">Enter the columns contributing to that table's primary key.</span></span>  
  
 <span data-ttu-id="bff94-121">**Grade abaixo da Tabela de Chaves Estrangeiras**</span><span class="sxs-lookup"><span data-stu-id="bff94-121">**Grid beneath Foreign Key Table**</span></span>  
 <span data-ttu-id="bff94-122">Lista as colunas da tabela selecionada na lista da **Tabela de Chaves Estrangeiras** .</span><span class="sxs-lookup"><span data-stu-id="bff94-122">List the columns of the table selected in the **Foreign Key Table** list.</span></span> <span data-ttu-id="bff94-123">Insira a coluna das chaves estrangeiras da tabela das chaves estrangeiras que corresponde à coluna das chaves primárias.</span><span class="sxs-lookup"><span data-stu-id="bff94-123">Enter the foreign-key column of the foreign-key table that corresponds to the primary key column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bff94-124">As colunas selecionadas para a chave estrangeira devem ter o mesmo tipo de dados das colunas primárias às quais elas correspondem.</span><span class="sxs-lookup"><span data-stu-id="bff94-124">The columns you choose for the foreign key must have the same data type of the primary columns they correspond to.</span></span> <span data-ttu-id="bff94-125">Deve haver um número igual de colunas em cada uma das chaves.</span><span class="sxs-lookup"><span data-stu-id="bff94-125">There must be an equal number of columns in each of the keys.</span></span> <span data-ttu-id="bff94-126">Por exemplo, se a chave primária da tabela no lado primário da relação estiver composta de duas colunas, será necessário coincidir cada uma dessas colunas com uma coluna na tabela no lado da chave estrangeira da relação.</span><span class="sxs-lookup"><span data-stu-id="bff94-126">For example, if the primary key of the table on the primary side of the relationship is made up of two columns, you will need to match each of those columns with a column in the table for the foreign key side of the relationship.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bff94-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bff94-127">See Also</span></span>  
 [<span data-ttu-id="bff94-128">Criar relações de chaves estrangeiras</span><span class="sxs-lookup"><span data-stu-id="bff94-128">Create Foreign Key Relationships</span></span>](../../relational-databases/tables/create-foreign-key-relationships.md)  
  
  
