---
title: Verificar o subsistema de saída de entrada de disco para problemas de repetição de leitura | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: cedf4097-5b73-4964-9935-74a101847019
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 19809b1554e435600eb4eeae424bed17dc27bdbb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678729"
---
# <a name="check-disk-input-output-subsystem-for-read-retry-problems"></a><span data-ttu-id="f683b-102">Verificar o subsistema de entrada e saída de disco para problemas de repetição de leitura</span><span class="sxs-lookup"><span data-stu-id="f683b-102">Check Disk Input Output Subsystem for Read Retry Problems</span></span>
  <span data-ttu-id="f683b-103">Esta regra verifica o log de eventos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para a mensagem de erro 825.</span><span class="sxs-lookup"><span data-stu-id="f683b-103">This rule checks the event log for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error message 825.</span></span> <span data-ttu-id="f683b-104">Esta mensagem indica que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não pôde ler os dados do disco na primeira tentativa.</span><span class="sxs-lookup"><span data-stu-id="f683b-104">This message indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] was unable to read data from the disk on the first try.</span></span> <span data-ttu-id="f683b-105">Esta mensagem indica um problema grave com o subsistema de E/S do disco.</span><span class="sxs-lookup"><span data-stu-id="f683b-105">This message indicates a major problem with the disk I/O subsystem.</span></span> <span data-ttu-id="f683b-106">Atualmente, esta mensagem não indica um problema no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f683b-106">This message does not currently indicate a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] problem.</span></span> <span data-ttu-id="f683b-107">Entretanto, o problema com o disco poderia causar perda de dados ou danos no banco de dados se não for resolvido.</span><span class="sxs-lookup"><span data-stu-id="f683b-107">However, the disk problem could cause data loss or database corruption if it is not resolved.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="f683b-108">Práticas Recomendadas</span><span class="sxs-lookup"><span data-stu-id="f683b-108">Best Practices Recommendations</span></span>  
 <span data-ttu-id="f683b-109">As ações a seguir podem ajudar a identificar e resolver o problema subjacente no hardware:</span><span class="sxs-lookup"><span data-stu-id="f683b-109">The following actions might help you discover and resolve the underlying hardware problem:</span></span>  
  
-   <span data-ttu-id="f683b-110">Revise o log de erros e o texto variável nesta mensagem para encontrar pistas que expliquem o problema.</span><span class="sxs-lookup"><span data-stu-id="f683b-110">Review the error log and the variable text in this message for clues that explain the problem.</span></span>  
  
-   <span data-ttu-id="f683b-111">Verifique o sistema de disco.</span><span class="sxs-lookup"><span data-stu-id="f683b-111">Check the disk system.</span></span> <span data-ttu-id="f683b-112">O problema pode estar relacionado aos discos, aos controladores de disco, aos cartões de matriz ou aos drivers de disco.</span><span class="sxs-lookup"><span data-stu-id="f683b-112">The problem could be related to the disks, the disk controllers, array cards, or disk drivers.</span></span>  
  
-   <span data-ttu-id="f683b-113">Contate o fabricante do disco para obter os mais recentes utilitários para verificar o status do sistema do disco.</span><span class="sxs-lookup"><span data-stu-id="f683b-113">Contact the disk manufacturer for the latest utilities for checking the status of the disk system.</span></span>  
  
-   <span data-ttu-id="f683b-114">Contate o fabricante do disco para obter as mais recentes atualizações de driver.</span><span class="sxs-lookup"><span data-stu-id="f683b-114">Contact the disk manufacturer for the latest driver updates.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="f683b-115">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="f683b-115">For More Information</span></span>  
 [<span data-ttu-id="f683b-116">MSSQLSERVER_825</span><span class="sxs-lookup"><span data-stu-id="f683b-116">MSSQLSERVER_825</span></span>](../errors-events/mssqlserver-825-database-engine-error.md)  
  
 <span data-ttu-id="f683b-117">[Fundamentos de E/S do SQL Server, Capítulo 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="f683b-117">[SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10))</span></span>  
  
  
