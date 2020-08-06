---
title: Especificar o primeiro e o último gatilho | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- first triggers [SQL Server]
- last triggers
- DML triggers, first or last triggers
- INSTEAD OF triggers
- AFTER triggers
ms.assetid: 9e6c7684-3dd3-46bb-b7be-523b33fae4d5
author: rothja
ms.author: jroth
ms.openlocfilehash: 8ddb352b00dc759362c8f6ef1e861e55b6f184f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582861"
---
# <a name="specify-first-and-last-triggers"></a><span data-ttu-id="48073-102">Especificar o primeiro e o último gatilhos</span><span class="sxs-lookup"><span data-stu-id="48073-102">Specify First and Last Triggers</span></span>
  <span data-ttu-id="48073-103">É possível especificar que um dos gatilhos AFTER associados a uma tabela seja tanto o primeiro gatilho AFTER quanto o último gatilho AFTER, acionado para cada uma das ações de gatilho - INSERT, DELETE e UPDATE.</span><span class="sxs-lookup"><span data-stu-id="48073-103">You can specify that one of the AFTER triggers associated with a table be either the first AFTER trigger or the last AFTER trigger that is fired for each INSERT, DELETE, and UPDATE triggering actions.</span></span> <span data-ttu-id="48073-104">Os disparadores AFTER que são acionados entre o primeiro e o último disparador são executados em ordem indefinida.</span><span class="sxs-lookup"><span data-stu-id="48073-104">The AFTER triggers that are fired between the first and last triggers are executed in undefined order.</span></span>  
  
 <span data-ttu-id="48073-105">Para especificar a ordem para um gatilho AFTER, use o procedimento armazenado **sp_settriggerorder** .</span><span class="sxs-lookup"><span data-stu-id="48073-105">To specify the order for an AFTER trigger, use the **sp_settriggerorder** stored procedure.</span></span> <span data-ttu-id="48073-106">**sp_settriggerorder** tem as opções a seguir.</span><span class="sxs-lookup"><span data-stu-id="48073-106">**sp_settriggerorder** has the following options.</span></span>  
  
|<span data-ttu-id="48073-107">Opção</span><span class="sxs-lookup"><span data-stu-id="48073-107">Option</span></span>|<span data-ttu-id="48073-108">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="48073-108">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="48073-109">**First**</span><span class="sxs-lookup"><span data-stu-id="48073-109">**First**</span></span>|<span data-ttu-id="48073-110">Especifica que o gatilho DML é o primeiro gatilho AFTER acionado para uma ação de gatilho.</span><span class="sxs-lookup"><span data-stu-id="48073-110">Specifies that the DML trigger is the first AFTER trigger fired for a triggering action.</span></span>|  
|<span data-ttu-id="48073-111">**Last**</span><span class="sxs-lookup"><span data-stu-id="48073-111">**Last**</span></span>|<span data-ttu-id="48073-112">Especifica que o gatilho DML é o último gatilho AFTER acionado para uma ação de gatilho.</span><span class="sxs-lookup"><span data-stu-id="48073-112">Specifies that the DML trigger is the last AFTER trigger fired for a triggering action.</span></span>|  
|<span data-ttu-id="48073-113">**Nenhuma**</span><span class="sxs-lookup"><span data-stu-id="48073-113">**None**</span></span>|<span data-ttu-id="48073-114">Especifica que não há nenhuma ordem específica na qual o gatilho DML deva ser acionado.</span><span class="sxs-lookup"><span data-stu-id="48073-114">Specifies that there is no specific order in which the DML trigger should be fired.</span></span> <span data-ttu-id="48073-115">Usado, principalmente, para redefinir um gatilho a ser o primeiro ou o último.</span><span class="sxs-lookup"><span data-stu-id="48073-115">Used mainly to reset a trigger from being either first or last.</span></span>|  
  
 <span data-ttu-id="48073-116">O seguinte exemplo mostra o uso de **sp_settriggerorder**:</span><span class="sxs-lookup"><span data-stu-id="48073-116">The following example shows using **sp_settriggerorder**:</span></span>  
  
```  
sp_settriggerorder @triggername = 'MyTrigger', @order = 'first', @stmttype = 'UPDATE'  
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="48073-117">O primeiro e o último gatilho devem ser dois gatilhos DML diferentes.</span><span class="sxs-lookup"><span data-stu-id="48073-117">The first and last triggers must be two different DML triggers.</span></span>  
  
 <span data-ttu-id="48073-118">Uma tabela pode definir os gatilhos INSERT, UPDATE, e DELETE para serem acionados ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="48073-118">A table can have INSERT, UPDATE, and DELETE triggers defined on it at the same time.</span></span> <span data-ttu-id="48073-119">Cada instrução pode ter seus próprios primeiros e últimos gatilhos, mas os gatilhos não podem ser os mesmos.</span><span class="sxs-lookup"><span data-stu-id="48073-119">Each statement type can have its own first and last triggers, but they cannot be the same triggers.</span></span>  
  
 <span data-ttu-id="48073-120">Caso o primeiro ou o último gatilho definido para uma tabela não abranja uma ação de gatilho, por exemplo, INSERT, DELETE e UPDATE, não haverá primeiro ou último gatilho para ações perdidas.</span><span class="sxs-lookup"><span data-stu-id="48073-120">If the first or last trigger defined for a table does not cover a triggering action, such as not covering FOR UPDATE, FOR DELETE, or FOR INSERT, there is no first or last trigger for the missing actions.</span></span>  
  
 <span data-ttu-id="48073-121">Gatilhos INSTEAD OF não podem ser especificados como primeiro ou último.</span><span class="sxs-lookup"><span data-stu-id="48073-121">INSTEAD OF triggers cannot be specified as first or last triggers.</span></span> <span data-ttu-id="48073-122">Os gatilhos INSTEAD OF são acionados antes que as atualizações das tabelas subjacentes sejam feitas.</span><span class="sxs-lookup"><span data-stu-id="48073-122">INSTEAD OF triggers are fired before updates are made to the underlying tables.</span></span> <span data-ttu-id="48073-123">Se as atualizações forem feitas pelo gatilho INSTEAD OF às tabelas subjacentes, as atualizações ocorrerão antes que qualquer gatilho AFTER, definido na tabela, seja acionado.</span><span class="sxs-lookup"><span data-stu-id="48073-123">If updates are made by an INSTEAD OF trigger to underlying tables, the updates occur before any AFTER triggers defined on the table are fired.</span></span> <span data-ttu-id="48073-124">Por exemplo, se um gatilho INSTEAD OF INSERT em uma exibição, inserir dados em uma tabela base e a tabela base tiver um gatilho INSTEAD OF INSERT e três gatilhos AFTER INSERT, o gatilho INSTEAD OF INSERT na tabela base, será acionado em vez da ação de inserção e os gatilhos AFTER na tabela base, serão acionados após qualquer ação de inserção na tabela base.</span><span class="sxs-lookup"><span data-stu-id="48073-124">For example, if an INSTEAD OF INSERT trigger on a view inserts data into a base table and the base table itself contains an INSTEAD OF INSERT trigger and three AFTER INSERT triggers, the INSTEAD OF INSERT trigger on the base table is fired instead of the inserting action, and the AFTER triggers on the base table are fired after any inserting action on the base table.</span></span> <span data-ttu-id="48073-125">Para obter mais informações, consulte [DML Triggers](dml-triggers.md).</span><span class="sxs-lookup"><span data-stu-id="48073-125">For more information, see [DML Triggers](dml-triggers.md).</span></span>  
  
 <span data-ttu-id="48073-126">Se uma instrução ALTER TRIGGER alterar o primeiro ou o último gatilho, os atributos **First** ou **Last** serão removidos e o valor do pedido será definido como **None**.</span><span class="sxs-lookup"><span data-stu-id="48073-126">If an ALTER TRIGGER statement changes a first or last trigger, the **First** or **Last** attribute is dropped and the order value is set to **None**.</span></span> <span data-ttu-id="48073-127">O pedido deve ser redefinido com **sp_settriggerorder**.</span><span class="sxs-lookup"><span data-stu-id="48073-127">The order must be reset by using **sp_settriggerorder**.</span></span>  
  
 <span data-ttu-id="48073-128">A função OBJECTPROPERTY informa se um gatilho é do tipo primeiro ou último por meio das propriedades **ExecIsFirstTrigger** e **ExecIsLastTrigger**.</span><span class="sxs-lookup"><span data-stu-id="48073-128">The OBJECTPROPERTY function reports whether a trigger is a first or last trigger by using the properties **ExecIsFirstTrigger** and **ExecIsLastTrigger**.</span></span>  
  
 <span data-ttu-id="48073-129">A replicação gera automaticamente um primeiro disparador para qualquer tabela que esteja incluída em uma atualização imediata ou uma assinatura de atualização em fila.</span><span class="sxs-lookup"><span data-stu-id="48073-129">Replication automatically generates a first trigger for any table that is included in an immediate updating or queued updating subscription.</span></span> <span data-ttu-id="48073-130">A replicação requer que seu disparador seja o primeiro disparador.</span><span class="sxs-lookup"><span data-stu-id="48073-130">Replication requires that its trigger be the first trigger.</span></span> <span data-ttu-id="48073-131">A replicação gerará um erro se você tentar incluir uma tabela com um primeiro disparador em uma atualização imediata ou uma assinatura de atualização em fila.</span><span class="sxs-lookup"><span data-stu-id="48073-131">Replication raises an error when you try to include a table with a first trigger in an immediate updating or queued updating subscription.</span></span> <span data-ttu-id="48073-132">Se você tentar fazer com que um gatilho seja o primeiro depois que uma tabela for incluída em uma assinatura, **sp_settriggerorder** retornará um erro.</span><span class="sxs-lookup"><span data-stu-id="48073-132">If you try to make a trigger a first trigger after a table has been included in a subscription, **sp_settriggerorder** returns an error.</span></span> <span data-ttu-id="48073-133">Se você usar ALTER no gatilho de replicação ou usar **sp_settriggerorder** para alterar o gatilho de replicação para o último ou nenhum gatilho, a assinatura não funcionará corretamente.</span><span class="sxs-lookup"><span data-stu-id="48073-133">If you use ALTER on the replication trigger or use **sp_settriggerorder** to change the replication trigger to a last or none trigger, the subscription will not function correctly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48073-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="48073-134">See Also</span></span>  
 <span data-ttu-id="48073-135">[OBJECTPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectpropertyex-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="48073-135">[OBJECTPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectpropertyex-transact-sql) </span></span>  
 [<span data-ttu-id="48073-136">sp_settriggerorder &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="48073-136">sp_settriggerorder &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-settriggerorder-transact-sql)  
  
  
