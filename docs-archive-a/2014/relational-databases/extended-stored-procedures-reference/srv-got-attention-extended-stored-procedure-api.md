---
title: srv_got_attention (API de Procedimento Armazenado Estendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_got_attention
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_got_attention
ms.assetid: 805e68e1-d17f-41bd-8b9f-a27283bb6fbe
author: rothja
ms.author: jroth
ms.openlocfilehash: bb5432e2f5e259187e506237842fbb9110e27a69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685716"
---
# <a name="srv_got_attention-extended-stored-procedure-api"></a><span data-ttu-id="9c061-102">srv_got_attention (API do procedimento armazenado estendido)</span><span class="sxs-lookup"><span data-stu-id="9c061-102">srv_got_attention (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="9c061-103">Em vez disso, use a Integração CLR.</span><span class="sxs-lookup"><span data-stu-id="9c061-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="9c061-104">Verifica se a tarefa ou a conexão atual precisa ser anulada e retorna TRUE se a conexão for interrompida ou se o lote for anulado</span><span class="sxs-lookup"><span data-stu-id="9c061-104">Checks whether the current connection or task needs to be aborted and returns TRUE if the connection is killed or the batch is aborted</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c061-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9c061-105">Syntax</span></span>  
  
```  
  
BOOL srv_got_attention  
(SRV_PROC *  
srvproc  
);  
  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9c061-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="9c061-106">Parameters</span></span>  
 <span data-ttu-id="9c061-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="9c061-107">*srvproc*</span></span>  
 <span data-ttu-id="9c061-108">Ponteiro que identifica uma conexão de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9c061-108">Pointer identifying a database connection.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9c061-109">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="9c061-109">Return Value</span></span>  
 <span data-ttu-id="9c061-110">TRUE se a conexão for interrompida ou se o lote for anulado.</span><span class="sxs-lookup"><span data-stu-id="9c061-110">TRUE if the connection is killed or the batch is aborted.</span></span> <span data-ttu-id="9c061-111">FALSE se a conexão ou o lote estiverem ativos.</span><span class="sxs-lookup"><span data-stu-id="9c061-111">FALSE if the connection or batch is active.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c061-112">Comentários</span><span class="sxs-lookup"><span data-stu-id="9c061-112">Remarks</span></span>  
 <span data-ttu-id="9c061-113">Um procedimento armazenado estendido de execução longa deve verificar a atenção do servidor chamando **srv_got_attention** periodicamente, de forma que o procedimento possa ser encerrado quando a conexão for interrompida ou o lote for anulado.</span><span class="sxs-lookup"><span data-stu-id="9c061-113">A long-running extended stored procedure should check the server attention by calling **srv_got_attention** periodically so that the procedure may terminate itself when the connection is killed or the batch is aborted.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9c061-114">Você deve examinar totalmente o código-fonte de procedimentos armazenados estendidos e deve testar as DLLs compiladas antes de instalá-las em um servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="9c061-114">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="9c061-115">Para obter informações sobre revisão e testes de segurança, consulte este [site da Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="9c061-115">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
