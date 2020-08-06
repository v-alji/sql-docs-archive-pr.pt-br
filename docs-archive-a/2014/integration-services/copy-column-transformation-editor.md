---
title: Editor de transformação copiar coluna | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.copymaptransformation.f1
helpviewer_keywords:
- Copy Column Transformation Editor
ms.assetid: d8e70541-d563-4ce4-bf66-bc888a0d3026
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7647d25891b37e5f09356d427072e84b45882e4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574840"
---
# <a name="copy-column-transformation-editor"></a><span data-ttu-id="3e2c3-102">Editor de Transformação Copiar Coluna</span><span class="sxs-lookup"><span data-stu-id="3e2c3-102">Copy Column Transformation Editor</span></span>
  <span data-ttu-id="3e2c3-103">Use a caixa de diálogo **Editor de Transformação Copiar Coluna** para selecionar colunas para copiar e nomear as novas colunas de saída.</span><span class="sxs-lookup"><span data-stu-id="3e2c3-103">Use the **Copy Column Transformation Editor** dialog box to select columns to copy and to assign names for the new output columns.</span></span>  
  
 <span data-ttu-id="3e2c3-104">Para saber mais sobre a transformação Copiar Colunas, consulte [Copy Column Transformation](data-flow/transformations/copy-column-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="3e2c3-104">To learn more about the Copy Column transformation, see [Copy Column Transformation](data-flow/transformations/copy-column-transformation.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3e2c3-105">Ao copiar apenas todos os dados de origem para um destino, poderá não ser necessário usar a transformação Copiar Coluna.</span><span class="sxs-lookup"><span data-stu-id="3e2c3-105">When you are simply copying all of your source data to a destination, it may not be necessary to use the Copy Column transformation.</span></span> <span data-ttu-id="3e2c3-106">Em alguns cenários, você pode conectar uma origem diretamente para um destino, quando nenhuma transformação de dados é requerida.</span><span class="sxs-lookup"><span data-stu-id="3e2c3-106">In some scenarios, you can connect a source directly to a destination, when no data transformation is required.</span></span> <span data-ttu-id="3e2c3-107">Nestas circunstâncias é frequentemente preferível usar o Assistente de Importação e Exportação do SQL Server para criar o pacote para você.</span><span class="sxs-lookup"><span data-stu-id="3e2c3-107">In these circumstances it is often preferable to use the SQL Server Import and Export Wizard to create your package for you.</span></span> <span data-ttu-id="3e2c3-108">Depois você pode aprimorar e reconfigurar o pacote conforme a necessidade.</span><span class="sxs-lookup"><span data-stu-id="3e2c3-108">Later you can enhance and reconfigure the package as needed.</span></span> <span data-ttu-id="3e2c3-109">Para obter mais informações, consulte [SQL Server Import and Export Wizard](import-export-data/import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="3e2c3-109">For more information, see [SQL Server Import and Export Wizard](import-export-data/import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="3e2c3-110">Opções</span><span class="sxs-lookup"><span data-stu-id="3e2c3-110">Options</span></span>  
 <span data-ttu-id="3e2c3-111">**Colunas de Entrada Disponíveis**</span><span class="sxs-lookup"><span data-stu-id="3e2c3-111">**Available Input Columns**</span></span>  
 <span data-ttu-id="3e2c3-112">Selecione as colunas para copiar, usando as caixas de seleção.</span><span class="sxs-lookup"><span data-stu-id="3e2c3-112">Select columns to copy by using the check boxes.</span></span> <span data-ttu-id="3e2c3-113">as seleções adicionam colunas de entrada à tabela abaixo.</span><span class="sxs-lookup"><span data-stu-id="3e2c3-113">Your selections add input columns to the table below.</span></span>  
  
 <span data-ttu-id="3e2c3-114">**Coluna de Entrada**</span><span class="sxs-lookup"><span data-stu-id="3e2c3-114">**Input Column**</span></span>  
 <span data-ttu-id="3e2c3-115">Selecione colunas para copiar na lista de colunas de entrada disponíveis.</span><span class="sxs-lookup"><span data-stu-id="3e2c3-115">Select columns to copy from the list of available input columns.</span></span> <span data-ttu-id="3e2c3-116">As seleções se refletem naquelas da caixa de seleção da tabela **Colunas de Entrada Disponíveis** .</span><span class="sxs-lookup"><span data-stu-id="3e2c3-116">Your selections are reflected in the check box selections in the **Available Input Columns** table.</span></span>  
  
 <span data-ttu-id="3e2c3-117">**Alias de Saída**</span><span class="sxs-lookup"><span data-stu-id="3e2c3-117">**Output Alias**</span></span>  
 <span data-ttu-id="3e2c3-118">Digite um alias para cada nova coluna de saída.</span><span class="sxs-lookup"><span data-stu-id="3e2c3-118">Type an alias for each new output column.</span></span> <span data-ttu-id="3e2c3-119">O padrão é **Copiar de**, seguido do nome da coluna de entrada; no entanto, é possível escolher qualquer nome descritivo exclusivo.</span><span class="sxs-lookup"><span data-stu-id="3e2c3-119">The default is **Copy of**, followed by the name of the input column; however, you can choose any unique, descriptive name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e2c3-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3e2c3-120">See Also</span></span>  
 [<span data-ttu-id="3e2c3-121">Referência de mensagens e erros do Integration Services</span><span class="sxs-lookup"><span data-stu-id="3e2c3-121">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
