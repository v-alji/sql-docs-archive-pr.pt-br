---
title: ICommand (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ICommand [SQL Server Native Client]
ms.assetid: 5e24b3a0-0658-44fc-b653-f4c52f9eb328
author: rothja
ms.author: jroth
ms.openlocfilehash: 03bdccc83a04078210f2283d0b330f237ed02979
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582441"
---
# <a name="icommand-ole-db"></a><span data-ttu-id="23ab9-102">ICommand (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="23ab9-102">ICommand (OLE DB)</span></span>
  <span data-ttu-id="23ab9-103">Este tópico aborda o comportamento OLE DB que é específico do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="23ab9-103">This topic discusses OLE DB behavior that is specific to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
## <a name="icommandexecute"></a><span data-ttu-id="23ab9-104">ICommand::Execute</span><span class="sxs-lookup"><span data-stu-id="23ab9-104">ICommand::Execute</span></span>  
 <span data-ttu-id="23ab9-105">Inserir dados maiores do que o tamanho de uma coluna normalmente resulta em um erro.</span><span class="sxs-lookup"><span data-stu-id="23ab9-105">Inserting data that is greater than the size of a column typically results in an error.</span></span> <span data-ttu-id="23ab9-106">No entanto, existem situações em que S_OK será retornado, mas *dwStatus* será definido como DBSTATUS_S_TRUNCATED.</span><span class="sxs-lookup"><span data-stu-id="23ab9-106">However, there are situations where S_OK will be returned but the *dwStatus* will be set to DBSTATUS_S_TRUNCATED.</span></span> <span data-ttu-id="23ab9-107">Isso geralmente ocorre quando os dados são inseridos com parâmetros, e a coluna não é grande o suficiente para manter os dados e `ICommandWithParameters::SetParameterInfo` não foi chamado.</span><span class="sxs-lookup"><span data-stu-id="23ab9-107">This generally occurs when inserting data with parameters, where the column is not large enough to hold the data, and `ICommandWithParameters::SetParameterInfo` has not been called.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23ab9-108">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="23ab9-108">See Also</span></span>  
 [<span data-ttu-id="23ab9-109">Interfaces &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="23ab9-109">Interfaces &#40;OLE DB&#41;</span></span>](../../database-engine/dev-guide/interfaces-ole-db.md)  
  
  
