---
title: Selecionar uma Tabela e Chaves de Dimensão (Assistente para Dimensões de Alteração Lenta) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.loaddimwizard.selecttableandkeys.f1
ms.assetid: 01e0495f-de35-4607-ba19-0539e801e8fd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 671c66a8a5d5f1f4f5201fd8c9ecc144540d8b68
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686346"
---
# <a name="select-a-dimension-table-and-keys-slowly-changing-dimension-wizard"></a><span data-ttu-id="f8ab1-102">Selecionar uma Tabela e Chaves de Dimensão (Assistente para Dimensões de Alteração Lenta)</span><span class="sxs-lookup"><span data-stu-id="f8ab1-102">Select a Dimension Table and Keys (Slowly Changing Dimension Wizard)</span></span>
  <span data-ttu-id="f8ab1-103">Use a página **Selecionar uma Tabela e Chaves de Dimensão** para selecionar uma tabela de dimensões a ser carregada.</span><span class="sxs-lookup"><span data-stu-id="f8ab1-103">Use the **Select a Dimension Table and Keys** page to select a dimension table to load.</span></span> <span data-ttu-id="f8ab1-104">Mapeie colunas do fluxo de dados para as colunas que serão carregadas.</span><span class="sxs-lookup"><span data-stu-id="f8ab1-104">Map columns from the data flow to the columns that will be loaded.</span></span>  
  
 <span data-ttu-id="f8ab1-105">Para obter mais informações sobre este assistente, consulte [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="f8ab1-105">To learn more about this wizard, see [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="f8ab1-106">Opções</span><span class="sxs-lookup"><span data-stu-id="f8ab1-106">Options</span></span>  
 <span data-ttu-id="f8ab1-107">**Connection manager**</span><span class="sxs-lookup"><span data-stu-id="f8ab1-107">**Connection manager**</span></span>  
 <span data-ttu-id="f8ab1-108">Selecione um gerenciador de conexões OLE DB existente na lista ou clique em **Novo** para criar um novo gerenciador de conexões OLE DB.</span><span class="sxs-lookup"><span data-stu-id="f8ab1-108">Select an existing OLE DB connection manager from the list, or click **New** to create an OLE DB connection manager.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f8ab1-109">O Assistente para Dimensão de Alteração Lenta dá suporte apenas a gerenciadores de conexões OLE DB e a conexões ao [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f8ab1-109">The Slowly Changing Dimension Wizard only supports OLE DB connection managers, and only supports connections to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="f8ab1-110">**Novo**</span><span class="sxs-lookup"><span data-stu-id="f8ab1-110">**New**</span></span>  
 <span data-ttu-id="f8ab1-111">Use a caixa de diálogo **Configurar Gerenciador de Conexões OLE DB** para selecionar um gerenciador de conexões existente ou clique em **Nova** para criar uma nova conexão OLE DB.</span><span class="sxs-lookup"><span data-stu-id="f8ab1-111">Use the **Configure OLE DB Connection Manager** dialog box to select an existing connection manager, or click **New** to create a new OLE DB connection.</span></span>  
  
 <span data-ttu-id="f8ab1-112">**Tabela ou Exibição**</span><span class="sxs-lookup"><span data-stu-id="f8ab1-112">**Table or View**</span></span>  
 <span data-ttu-id="f8ab1-113">Selecione uma tabela ou exibição da lista.</span><span class="sxs-lookup"><span data-stu-id="f8ab1-113">Select a table or view from the list.</span></span>  
  
 <span data-ttu-id="f8ab1-114">**Colunas de Entrada**</span><span class="sxs-lookup"><span data-stu-id="f8ab1-114">**Input Columns**</span></span>  
 <span data-ttu-id="f8ab1-115">Selecione na lista as colunas de entrada para as quais você pode especificar mapeamento.</span><span class="sxs-lookup"><span data-stu-id="f8ab1-115">Select from the list of input columns for which you may specify mapping.</span></span>  
  
 <span data-ttu-id="f8ab1-116">**Colunas de Dimensão**</span><span class="sxs-lookup"><span data-stu-id="f8ab1-116">**Dimension Columns**</span></span>  
 <span data-ttu-id="f8ab1-117">Exiba todas as colunas de dimensão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="f8ab1-117">View all available dimension columns.</span></span>  
  
 <span data-ttu-id="f8ab1-118">**Tipo de Chave**</span><span class="sxs-lookup"><span data-stu-id="f8ab1-118">**Key Type**</span></span>  
 <span data-ttu-id="f8ab1-119">Selecione uma das colunas de dimensão para servir de chave de negócio.</span><span class="sxs-lookup"><span data-stu-id="f8ab1-119">Select one of the dimension columns to be the business key.</span></span> <span data-ttu-id="f8ab1-120">É necessário possuir uma chave de negócio.</span><span class="sxs-lookup"><span data-stu-id="f8ab1-120">You must have one business key.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8ab1-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f8ab1-121">See Also</span></span>  
 [<span data-ttu-id="f8ab1-122">Configurar saídas por meio do Assistente para Dimensões de Alteração Lenta</span><span class="sxs-lookup"><span data-stu-id="f8ab1-122">Configure Outputs Using the Slowly Changing Dimension Wizard</span></span>](configure-outputs-using-the-slowly-changing-dimension-wizard.md)  
  
  
