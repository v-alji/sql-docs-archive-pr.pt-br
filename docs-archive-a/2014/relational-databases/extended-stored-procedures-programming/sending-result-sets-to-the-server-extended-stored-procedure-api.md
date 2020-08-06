---
title: Enviando conjuntos de resultados para o servidor (API de procedimento armazenado estendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], sending result sets
- result sets [SQL Server], extended stored procedures
ms.assetid: 9d54673d-ea9d-4ac6-825a-f216ad8b0e34
author: rothja
ms.author: jroth
ms.openlocfilehash: 82984440f96416189eb18f900764ee7bdaf05a01
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568576"
---
# <a name="sending-result-sets-to-the-server-extended-stored-procedure-api"></a><span data-ttu-id="97acd-102">Enviando conjuntos de resultados ao Servidor (API do procedimento armazenado estendido)</span><span class="sxs-lookup"><span data-stu-id="97acd-102">Sending Result Sets to the Server (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="97acd-103">Em vez disso, use a integração CLR.</span><span class="sxs-lookup"><span data-stu-id="97acd-103">Use CLR Integration instead.</span></span>  
  
 <span data-ttu-id="97acd-104">Ao enviar um conjunto de resultados para [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , o procedimento armazenado estendido deve chamar a API apropriada da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="97acd-104">When sending a result set to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the extended stored procedure should call the appropriate API as follows:</span></span>  
  
-   <span data-ttu-id="97acd-105">A função **srv_sendmsg** pode ser chamada em qualquer ordem antes ou depois de todas as linhas (se houver) terem sido enviadas com **srv_sendrow**.</span><span class="sxs-lookup"><span data-stu-id="97acd-105">The **srv_sendmsg** function may be called in any order before or after all rows (if any) have been sent with **srv_sendrow**.</span></span> <span data-ttu-id="97acd-106">Todas as mensagens devem ser enviadas ao cliente antes que o status de conclusão seja enviado com **srv_senddone**.</span><span class="sxs-lookup"><span data-stu-id="97acd-106">All messages must be sent to the client before the completion status is sent with **srv_senddone**.</span></span>  
  
-   <span data-ttu-id="97acd-107">A função **srv_sendrow** é chamada uma vez para cada linha enviada ao cliente.</span><span class="sxs-lookup"><span data-stu-id="97acd-107">The **srv_sendrow** function is called once for each row sent to the client.</span></span> <span data-ttu-id="97acd-108">Todas as linhas devem ser enviadas ao cliente antes que quaisquer mensagens, valores de status ou status de conclusão sejam enviados com **srv_sendmsg**, o argumento **srv_status** de **srv_pfield**ou **srv_senddone**.</span><span class="sxs-lookup"><span data-stu-id="97acd-108">All rows must be sent to the client before any messages, status values, or completion statuses are sent with **srv_sendmsg**, the **srv_status** argument of **srv_pfield**, or **srv_senddone**.</span></span>  
  
-   <span data-ttu-id="97acd-109">O envio de uma linha que não tinha todas as suas colunas definidas com **srv_describe** faz com que o aplicativo gere uma mensagem de erro informativa e retorne a falha para o cliente.</span><span class="sxs-lookup"><span data-stu-id="97acd-109">Sending a row that has not had all its columns defined with **srv_describe** causes the application to raise an informational error message and return FAIL to the client.</span></span> <span data-ttu-id="97acd-110">Neste caso, a linha não é enviada.</span><span class="sxs-lookup"><span data-stu-id="97acd-110">In this case, the row is not sent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97acd-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="97acd-111">See Also</span></span>  
 [<span data-ttu-id="97acd-112">Criando procedimentos armazenados estendidos</span><span class="sxs-lookup"><span data-stu-id="97acd-112">Creating Extended Stored Procedures</span></span>](creating-extended-stored-procedures.md)  
  
  
