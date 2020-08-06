---
title: Propriedades do banco de dados (página Controle de Alterações) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.databaseproperties.changetracking.f1
ms.assetid: 9b929640-bc62-449b-9b06-b5a77b8cf372
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4107f81ef4cdf19df60d4a70d8e79007f2c9270c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681684"
---
# <a name="database-properties-changetracking-page"></a><span data-ttu-id="c9039-102">Propriedades do Banco de Dados (página Controle de Alterações)</span><span class="sxs-lookup"><span data-stu-id="c9039-102">Database Properties (ChangeTracking Page)</span></span>
  <span data-ttu-id="c9039-103">Use essa página para exibir ou modificar configurações de controle de alterações para o banco de dados selecionado.</span><span class="sxs-lookup"><span data-stu-id="c9039-103">Use this page to view or modify change tracking settings for the selected database.</span></span> <span data-ttu-id="c9039-104">Para obter mais informações sobre as opções disponíveis nessa página, veja [Habilitar e desabilitar o controle de alterações &#40;SQL Server&#41;](../track-changes/enable-and-disable-change-tracking-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c9039-104">For more information about the options available on this page, see [Enable and Disable Change Tracking &#40;SQL Server&#41;](../track-changes/enable-and-disable-change-tracking-sql-server.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="c9039-105">Opções</span><span class="sxs-lookup"><span data-stu-id="c9039-105">Options</span></span>  
 <span data-ttu-id="c9039-106">**Controle de alterações**</span><span class="sxs-lookup"><span data-stu-id="c9039-106">**Change Tracking**</span></span>  
 <span data-ttu-id="c9039-107">Use para habilitar ou desabilitar o controle de alterações para o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c9039-107">Use to enable or disable change tracking for the database.</span></span>  
  
 <span data-ttu-id="c9039-108">Para habilitar o controle de alterações, deve-se ter permissão para modificar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c9039-108">To enable change tracking, you must have permission to modify the database.</span></span>  
  
 <span data-ttu-id="c9039-109">Definindo-se o valor como **Verdadeiro** define-se uma opção de banco de dados que permite que o controle de alterações seja habilitado em tabelas individuais.</span><span class="sxs-lookup"><span data-stu-id="c9039-109">Setting the value to **True** sets a database option that allows change tracking to be enabled on individual tables.</span></span>  
  
 <span data-ttu-id="c9039-110">Pode-se também configurar o controle de alterações usando [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c9039-110">You can also configure change tracking by using [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
 <span data-ttu-id="c9039-111">**Período de Retenção**</span><span class="sxs-lookup"><span data-stu-id="c9039-111">**Retention Period**</span></span>  
 <span data-ttu-id="c9039-112">Especifica o período mínimo para manter informações de controle de alterações no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c9039-112">Specifies the minimum period for keeping change track information in the database.</span></span> <span data-ttu-id="c9039-113">Os dados serão removidos somente se o valor **Auto Clean-Up**for **True**.</span><span class="sxs-lookup"><span data-stu-id="c9039-113">Data is removed only if the **Auto Clean-Up**value is **True**.</span></span>  
  
 <span data-ttu-id="c9039-114">O valor padrão é 2.</span><span class="sxs-lookup"><span data-stu-id="c9039-114">The default value is 2.</span></span>  
  
 <span data-ttu-id="c9039-115">**Unidades de Período de Retenção**</span><span class="sxs-lookup"><span data-stu-id="c9039-115">**Retention Period Units**</span></span>  
 <span data-ttu-id="c9039-116">Especifica as unidades para o valor de período de retenção.</span><span class="sxs-lookup"><span data-stu-id="c9039-116">Specifies the units for the Retention Period value.</span></span> <span data-ttu-id="c9039-117">Pode-se selecionar **Dias**, **Horas**ou **Minutos**.</span><span class="sxs-lookup"><span data-stu-id="c9039-117">You can select **Days**, **Hours**, or **Minutes**.</span></span> <span data-ttu-id="c9039-118">O valor padrão é **Dias**.</span><span class="sxs-lookup"><span data-stu-id="c9039-118">The default value is **Days**.</span></span>  
  
 <span data-ttu-id="c9039-119">O período de retenção mínimo é de 1 minuto.</span><span class="sxs-lookup"><span data-stu-id="c9039-119">The minimum retention period is 1 minute.</span></span> <span data-ttu-id="c9039-120">Não há um período máximo de retenção.</span><span class="sxs-lookup"><span data-stu-id="c9039-120">There is no maximum retention period.</span></span>  
  
 <span data-ttu-id="c9039-121">**Auto Clean-Up**</span><span class="sxs-lookup"><span data-stu-id="c9039-121">**Auto Clean-Up**</span></span>  
 <span data-ttu-id="c9039-122">Indica se as informações de controle de alterações são automaticamente removidas depois do período de retenção especificado.</span><span class="sxs-lookup"><span data-stu-id="c9039-122">Indicates whether change tracking information is automatically removed after the specified retention period.</span></span>  
  
 <span data-ttu-id="c9039-123">Habilitar a opção **Auto Clean-Up** redefine qualquer período de retenção personalizado anterior ao período de retenção padrão de 2 dias.</span><span class="sxs-lookup"><span data-stu-id="c9039-123">Enabling **Auto Clean-Up** resets any previous custom retention period to the default retention period of 2 days.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9039-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c9039-124">See Also</span></span>  
 <span data-ttu-id="c9039-125">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c9039-125">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="c9039-126">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c9039-126">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-sql-server-transact-sql)  
  
  
