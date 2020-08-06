---
title: Trabalhando com objetos de banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- database objects [SMO]
- objects [SMO]
ms.assetid: 702fd63d-8734-4a02-872e-aecfb037c787
author: stevestein
ms.author: sstein
ms.openlocfilehash: 14dd0c0175a23f809fc925c5104ac15ac408805b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684641"
---
# <a name="working-with-database-objects"></a><span data-ttu-id="f5b91-102">Trabalhando com objetos de banco de dados</span><span class="sxs-lookup"><span data-stu-id="f5b91-102">Working with Database Objects</span></span>
  <span data-ttu-id="f5b91-103">As fases da criação de objetos SMO são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="f5b91-103">The stages of SMO object creation are as follows:</span></span>  
  
1.  <span data-ttu-id="f5b91-104">Criar uma instância do objeto.</span><span class="sxs-lookup"><span data-stu-id="f5b91-104">Create an instance of the object.</span></span>  
  
2.  <span data-ttu-id="f5b91-105">Definir as propriedades do objeto.</span><span class="sxs-lookup"><span data-stu-id="f5b91-105">Set the object properties.</span></span>  
  
3.  <span data-ttu-id="f5b91-106">Criar instâncias dos objetos filhos.</span><span class="sxs-lookup"><span data-stu-id="f5b91-106">Create instances of the child objects.</span></span>  
  
4.  <span data-ttu-id="f5b91-107">Definir as propriedades dos objetos filhos.</span><span class="sxs-lookup"><span data-stu-id="f5b91-107">Set the child object properties.</span></span>  
  
5.  <span data-ttu-id="f5b91-108">Criar o objeto.</span><span class="sxs-lookup"><span data-stu-id="f5b91-108">Create the object.</span></span>  
  
 <span data-ttu-id="f5b91-109">Quando são criadas instâncias de objetos SMO em um aplicativo SMO, elas não existem na instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] até que o método `Create` seja emitido.</span><span class="sxs-lookup"><span data-stu-id="f5b91-109">When instances of SMO objects are created in an SMO application, they do not exist on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] until the `Create` method is issued.</span></span> <span data-ttu-id="f5b91-110">Porém, não é necessário emitir um método `Create` para cada objeto individual.</span><span class="sxs-lookup"><span data-stu-id="f5b91-110">However, it is not necessary to issue a `Create` method for every individual object.</span></span> <span data-ttu-id="f5b91-111">Se um objeto tiver um conjunto de objetos filhos, apenas o objeto pai será necessário para executar o método `Create`.</span><span class="sxs-lookup"><span data-stu-id="f5b91-111">If an object has a set of child objects, only the parent object is required to run the `Create` method.</span></span> <span data-ttu-id="f5b91-112">Por exemplo, a definição de uma tabela exige que ela contenha pelo menos uma coluna para existir.</span><span class="sxs-lookup"><span data-stu-id="f5b91-112">For example, the definition of a table requires that it contains at least one column to exist.</span></span> <span data-ttu-id="f5b91-113">Além disso, uma coluna não pode existir em isolamento sem uma tabela.</span><span class="sxs-lookup"><span data-stu-id="f5b91-113">Also, a column cannot exist in isolation without a table.</span></span> <span data-ttu-id="f5b91-114">Há uma relação codependente entre a tabela e suas colunas.</span><span class="sxs-lookup"><span data-stu-id="f5b91-114">There is a codependent relationship between the table and its columns.</span></span>  
  
 <span data-ttu-id="f5b91-115">O método <xref:Microsoft.SqlServer.Management.Dmf.Policy.Alter%2A> permite fazer alterações a um objeto.</span><span class="sxs-lookup"><span data-stu-id="f5b91-115">The <xref:Microsoft.SqlServer.Management.Dmf.Policy.Alter%2A> method lets you make changes to an object.</span></span> <span data-ttu-id="f5b91-116">Várias alterações a um objeto, como a adição de objetos filhos a uma das coleções do objeto ou a alteração de um valor de propriedade, são colocados em lotes e executados de uma vez.</span><span class="sxs-lookup"><span data-stu-id="f5b91-116">Several changes to an object, such as adding child objects to one of the object's collections or changing a property value, are batched together and run as one.</span></span> <span data-ttu-id="f5b91-117">O método `Alter` reduz o tráfego de rede e aprimora o desempenho geral.</span><span class="sxs-lookup"><span data-stu-id="f5b91-117">The `Alter` method reduces network traffic and improves overall performance.</span></span>  
  
 <span data-ttu-id="f5b91-118">A instrução `Drop` é usada para remover um objeto e todos os seus objetos filhos codependentes que foram necessário para criar o objeto inicialmente.</span><span class="sxs-lookup"><span data-stu-id="f5b91-118">The `Drop` statement is used to remove an object and all its codependent child objects that were required to create the object initially.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5b91-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f5b91-119">See Also</span></span>  
 [<span data-ttu-id="f5b91-120">Modelo de objeto SMO</span><span class="sxs-lookup"><span data-stu-id="f5b91-120">SMO Object Model</span></span>](../smo-object-model.md)  
  
  
