---
title: Fazer alterações nas tabelas selecionadas para capturar alterações | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- makChanToTab
ms.assetid: a309f82a-c6ef-464d-a6ef-df555bfb609a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 258eb8e761ac697bebd630cc0e627941b4ffc7d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571517"
---
# <a name="make-changes-to-the-tables-selected-for-capturing-changes"></a><span data-ttu-id="16086-102">Fazer alterações às tabelas selecionadas para capturar alterações</span><span class="sxs-lookup"><span data-stu-id="16086-102">Make Changes to the Tables Selected for Capturing Changes</span></span>
  <span data-ttu-id="16086-103">Nesta caixa de diálogo, você pode selecionar colunas específicas da tabela selecionada da qual capturar alterações.</span><span class="sxs-lookup"><span data-stu-id="16086-103">In this dialog box, you can select specific columns from the selected table to capture changes from.</span></span> <span data-ttu-id="16086-104">Você também pode editar as informações de **Função de Segurança** e **Instância de Captura** .</span><span class="sxs-lookup"><span data-stu-id="16086-104">You can also edit the **Security Role** and **Capture Instance** information.</span></span>  
  
 <span data-ttu-id="16086-105">Você pode fazer as seguintes alterações nas tabelas selecionadas para capturar alterações nessa caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="16086-105">You can make the following changes to the tables you selected for capturing changes in this dialog box.</span></span>  
  
 <span data-ttu-id="16086-106">**Faça alterações para quais colunas são incluídas na instância CDC:**</span><span class="sxs-lookup"><span data-stu-id="16086-106">**Make changes to which columns are included in the CDC instance:**</span></span>  
  
 <span data-ttu-id="16086-107">Siga um ou ambos destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="16086-107">Do one or both of the following:</span></span>  
  
-   <span data-ttu-id="16086-108">Marque a caixa de seleção ao lado de qualquer coluna adicional que você quer incluir.</span><span class="sxs-lookup"><span data-stu-id="16086-108">Select the check box next to any additional column you want to include.</span></span>  
  
-   <span data-ttu-id="16086-109">Desmarque a caixa de seleção ao lado de qualquer coluna que você não quer mais incluir.</span><span class="sxs-lookup"><span data-stu-id="16086-109">Clear the check box next to any column that you no longer want to include.</span></span>  
  
 <span data-ttu-id="16086-110">**Alterar o tipo de dados para uma coluna específica**:</span><span class="sxs-lookup"><span data-stu-id="16086-110">**Change the data type for a specific column**:</span></span>  
  
 <span data-ttu-id="16086-111">Você pode selecionar um tipo de dados diferente para uma coluna específica.</span><span class="sxs-lookup"><span data-stu-id="16086-111">You can select a different data type for a specific column.</span></span> <span data-ttu-id="16086-112">Você pode alterar somente o tipo de dados para um tipo de dados que seja compatível com o tipo de dados original.</span><span class="sxs-lookup"><span data-stu-id="16086-112">You can only change the data type to a data type that is compatible with the original data type.</span></span>  
  
 <span data-ttu-id="16086-113">Para alterar o tipo de dados, clique na coluna **Tipo de Dados** e selecione um tipo de dados diferente.</span><span class="sxs-lookup"><span data-stu-id="16086-113">To change the data type, click in the **Data Type** column and select a different data type.</span></span> <span data-ttu-id="16086-114">Somente os tipos de dados que são compatível com o tipo de dados original estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="16086-114">Only data types that are compatible with the original data type are available.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="16086-115">Se nenhum tipo de dados adicional puder ser selecionado, a lista suspensa não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="16086-115">If no additional data types can be selected, the drop-down list is not available.</span></span>  
  
 <span data-ttu-id="16086-116">**Alterar a função de segurança**</span><span class="sxs-lookup"><span data-stu-id="16086-116">**Change the Security Role**</span></span>  
  
 <span data-ttu-id="16086-117">Digite um novo nome ou edite o nome da função de associação de segurança no campo **Função de Segurança** .</span><span class="sxs-lookup"><span data-stu-id="16086-117">Type a new name or edit the name of the security gating role in the **Security Role** field.</span></span>  
  
 <span data-ttu-id="16086-118">**Altere ou adicione uma instância de captura**</span><span class="sxs-lookup"><span data-stu-id="16086-118">**Change or add a capture instance**</span></span>  
  
 <span data-ttu-id="16086-119">No campo **Instância de Captura** , insira um nome para a instância de captura.</span><span class="sxs-lookup"><span data-stu-id="16086-119">In the **Capture Instance** field enter a name for the capture instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16086-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="16086-120">See Also</span></span>  
 <span data-ttu-id="16086-121">[Como criar a instância de banco de dados de alteração do SQL Server](how-to-create-the-sql-server-change-database-instance.md) </span><span class="sxs-lookup"><span data-stu-id="16086-121">[How to Create the SQL Server Change Database Instance](how-to-create-the-sql-server-change-database-instance.md) </span></span>  
 [<span data-ttu-id="16086-122">Selecionar tabelas e colunas Oracle</span><span class="sxs-lookup"><span data-stu-id="16086-122">Select Oracle Tables and Columns</span></span>](select-oracle-tables-and-columns.md)  
  
  
