---
title: Códigos de retorno | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB error handling, return codes
- SQL Server Native Client OLE DB provider, errors
- failed function [OLE DB]
- successful function [OLE DB]
- S_FALSE
- IS_ERROR macro
- DB_S_ERRORSOCCURRED return
- return codes [OLE DB]
- S_OK
- FAILED macro
- errors [OLE DB], return codes
ms.assetid: 7f7457e9-fce4-400c-82e5-ee02e9e811c6
author: rothja
ms.author: jroth
ms.openlocfilehash: dd033d16b1e95773d2cab1c4e1fca733dc491b96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581786"
---
# <a name="return-codes"></a><span data-ttu-id="4589b-102">Códigos de retorno</span><span class="sxs-lookup"><span data-stu-id="4589b-102">Return Codes</span></span>
  <span data-ttu-id="4589b-103">No nível mais básico, uma função de membro tem êxito ou falha.</span><span class="sxs-lookup"><span data-stu-id="4589b-103">At the most basic level, a member function either succeeds or fails.</span></span> <span data-ttu-id="4589b-104">Em um nível um pouco mais preciso, uma função pode ser bem-sucedida, mas talvez seu êxito não seja o desejado pelo desenvolvedor do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="4589b-104">At a somewhat more precise level, a function can succeed, but its success may not be what the application developer intended.</span></span>  
  
 <span data-ttu-id="4589b-105">Para obter mais informações sobre códigos de retorno do OLE DB, confira [Códigos de retorno (OLE DB)](https://go.microsoft.com/fwlink/?LinkId=101631).</span><span class="sxs-lookup"><span data-stu-id="4589b-105">For more information about OLE DB return codes, see [Return Codes (OLE DB)](https://go.microsoft.com/fwlink/?LinkId=101631).</span></span>  
  
 <span data-ttu-id="4589b-106">Quando uma [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] função de membro de provedor de OLE DB de cliente nativo retorna S_OK, a função foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="4589b-106">When a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider member function returns S_OK, the function succeeded.</span></span>  
  
 <span data-ttu-id="4589b-107">Quando uma [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] função de membro de provedor de OLE DB de cliente nativo não retorna S_OK, o OLE/com HRESULT-desempacotamento falhou e IS_ERROR macros podem determinar o êxito geral ou a falha de uma função.</span><span class="sxs-lookup"><span data-stu-id="4589b-107">When a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider member function does not return S_OK, the OLE/COM HRESULT-unpacking FAILED and IS_ERROR macros can determine the overall success or failure of a function.</span></span>  
  
 <span data-ttu-id="4589b-108">Se a falha ou IS_ERROR retornar TRUE, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consumidor do provedor de OLE DB de cliente nativo terá a garantia de que a execução da função de membro falhou.</span><span class="sxs-lookup"><span data-stu-id="4589b-108">If FAILED or IS_ERROR returns TRUE, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer is assured that member function execution failed.</span></span> <span data-ttu-id="4589b-109">Quando com falha ou IS_ERROR retornar FALSE e o HRESULT não for igual a S_OK, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cliente do provedor de OLE DB do Native Client terá certeza de que a função teve êxito em algum sentido.</span><span class="sxs-lookup"><span data-stu-id="4589b-109">When FAILED or IS_ERROR return FALSE and the HRESULT does not equal S_OK, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer is assured that the function succeeded in some sense.</span></span> <span data-ttu-id="4589b-110">O consumidor pode recuperar informações detalhadas sobre esse retorno de "êxito com informações" das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] interfaces de erro do provedor de OLE DB de cliente nativo.</span><span class="sxs-lookup"><span data-stu-id="4589b-110">The consumer can retrieve detailed information on this "success with information" return from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider error interfaces.</span></span> <span data-ttu-id="4589b-111">Além disso, no caso em que uma função falha claramente (a macro com falha retorna TRUE), as informações de erro estendidas estão disponíveis nas [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] interfaces de erro do provedor de OLE DB de cliente nativo.</span><span class="sxs-lookup"><span data-stu-id="4589b-111">Also, in the case where a function clearly fails (the FAILED macro returns TRUE), extended error information is available from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider error interfaces.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="4589b-112">Os consumidores do provedor de OLE DB de cliente nativo geralmente encontram o DB_S_ERRORSOCCURRED "sucesso com informações" de retorno de HRESULT.</span><span class="sxs-lookup"><span data-stu-id="4589b-112">Native Client OLE DB provider consumers commonly encounter the DB_S_ERRORSOCCURRED "success with information" HRESULT return.</span></span> <span data-ttu-id="4589b-113">Normalmente, funções de membro que retornam DB_S_ERRORSOCCURRED definem um ou mais parâmetros que fornecem valores de status ao consumidor.</span><span class="sxs-lookup"><span data-stu-id="4589b-113">Typically, member functions that return DB_S_ERRORSOCCURRED define one or more parameters that deliver status values to the consumer.</span></span> <span data-ttu-id="4589b-114">Talvez nenhuma informação de erro esteja disponível para o consumidor além daquela retornada em parâmetros de valor de status; assim, os consumidores devem implementar a lógica de aplicativo para recuperar valores de status quando eles estiverem disponíveis.</span><span class="sxs-lookup"><span data-stu-id="4589b-114">No error information may be available to the consumer other than that returned in status-value parameters, so consumers should implement application logic to retrieve status values when they are available.</span></span>  
  
 <span data-ttu-id="4589b-115">As [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] funções de membro do provedor de OLE DB de cliente nativo não retornam o código de êxito S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="4589b-115">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider member functions do not return the success code S_FALSE.</span></span> <span data-ttu-id="4589b-116">Todas as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] funções de membro do provedor de OLE DB de cliente nativo sempre retornam S_OK para indicar êxito.</span><span class="sxs-lookup"><span data-stu-id="4589b-116">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider member functions always return S_OK to indicate success.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4589b-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4589b-117">See Also</span></span>  
 [<span data-ttu-id="4589b-118">Erros</span><span class="sxs-lookup"><span data-stu-id="4589b-118">Errors</span></span>](errors.md)  
  
  
