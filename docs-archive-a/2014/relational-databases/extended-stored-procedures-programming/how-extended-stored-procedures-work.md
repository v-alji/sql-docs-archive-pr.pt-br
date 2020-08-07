---
title: Como funcionam os procedimentos armazenados estendidos | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], about extended stored procedures
ms.assetid: 6e946d8c-3268-4b59-8a1c-1637909cd701
author: rothja
ms.author: jroth
ms.openlocfilehash: 75082fed6b70c214b4f55b85034ffa371824d24f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576397"
---
# <a name="how-extended-stored-procedures-work"></a><span data-ttu-id="a9a43-102">Como funcionam os procedimentos armazenados estendidos</span><span class="sxs-lookup"><span data-stu-id="a9a43-102">How Extended Stored Procedures Work</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="a9a43-103">Em vez disso, use a integração CLR.</span><span class="sxs-lookup"><span data-stu-id="a9a43-103">Use CLR Integration instead.</span></span>  
  
 <span data-ttu-id="a9a43-104">O processo pelo qual um procedimento armazenado estendido funciona é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a9a43-104">The process by which an extended stored procedure works is:</span></span>  
  
1.  <span data-ttu-id="a9a43-105">Quando um cliente executa um procedimento armazenado estendido, a solicitação é transmitida no protocolo TDS ou no formato SOAP (Simple Object Access Protocol) do aplicativo cliente para o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a9a43-105">When a client executes an extended stored procedure, the request is transmitted in tabular data stream (TDS) or Simple Object Access Protocol (SOAP) format from the client application to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="a9a43-106">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pesquisa a DLL associada com o procedimento armazenado estendido e carrega a DLL, se ela já não estiver carregada.</span><span class="sxs-lookup"><span data-stu-id="a9a43-106">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] searches for the DLL associated with the extended stored procedure, and loads the DLL if it is not already loaded.</span></span>  
  
3.  <span data-ttu-id="a9a43-107">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] chama o procedimento armazenado estendido solicitado (implementado como uma função dentro da DLL).</span><span class="sxs-lookup"><span data-stu-id="a9a43-107">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] calls the requested extended stored procedure (implemented as a function inside the DLL).</span></span>  
  
4.  <span data-ttu-id="a9a43-108">O procedimento armazenado estendido passa conjuntos de resultados e parâmetros de retorno de volta ao servidor por meio da API de procedimento armazenado estendido.</span><span class="sxs-lookup"><span data-stu-id="a9a43-108">The extended stored procedure passes result sets and return parameters back to the server by through the Extended Stored Procedure API.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9a43-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a9a43-109">See Also</span></span>  
 [<span data-ttu-id="a9a43-110">Programação do procedimento armazenado estendido do mecanismo do banco de dados</span><span class="sxs-lookup"><span data-stu-id="a9a43-110">Database Engine Extended Stored Procedure Programming</span></span>](../database-engine-extended-stored-procedure-programming.md)  
  
  
