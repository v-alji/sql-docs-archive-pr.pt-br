---
title: Detalhes do erro do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, errors
- errors [OLE DB], error details
- IErrorRecords interface
- IErrorInfo interface
- OLE DB error handling, error details
- ISQLServerErrorInfo interface
ms.assetid: 51500ee3-3d78-47ec-b90f-ebfc55642e06
author: rothja
ms.author: jroth
ms.openlocfilehash: 4c03cf62dd274f9bcca213d33fb8969b26c9d980
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581785"
---
# <a name="sql-server-error-detail"></a><span data-ttu-id="e4f81-102">Detalhes de erros do SQL Server</span><span class="sxs-lookup"><span data-stu-id="e4f81-102">SQL Server Error Detail</span></span>
  <span data-ttu-id="e4f81-103">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo define a interface de erro específica do provedor [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="e4f81-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider defines the provider-specific error interface [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md).</span></span> <span data-ttu-id="e4f81-104">A interface retorna mais detalhes sobre um erro do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e é valiosa em caso de falha na execução de comandos ou em operações do conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="e4f81-104">The interface returns more detail about a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error and is valuable when command execution or rowset operations fail.</span></span>  
  
 <span data-ttu-id="e4f81-105">Há dois modos de obter acesso à interface **ISQLServerErrorInfo**.</span><span class="sxs-lookup"><span data-stu-id="e4f81-105">There are two ways to obtain access to **ISQLServerErrorInfo** interface.</span></span>  
  
 <span data-ttu-id="e4f81-106">O consumidor pode chamar **IErrorRecords::GetCustomerErrorObject** para obter um ponteiro **ISQLServerErrorInfo**, conforme mostrado no exemplo de código a seguir.</span><span class="sxs-lookup"><span data-stu-id="e4f81-106">The consumer may call **IErrorRecords::GetCustomerErrorObject** to obtain an **ISQLServerErrorInfo** pointer, as shown in the following code sample.</span></span> <span data-ttu-id="e4f81-107">(Não há necessidade de obter **ISQLErrorInfo**). **ISQLErrorInfo** e **ISQLServerErrorInfo** são objetos de erro personalizados do OLE DB, com **ISQLServerErrorInfo** sendo a interface a ser usada para obter informações de erros do servidor, incluindo detalhes como nome de procedimento e números de linha.</span><span class="sxs-lookup"><span data-stu-id="e4f81-107">(There is no need to obtain **ISQLErrorInfo.**) Both **ISQLErrorInfo** and **ISQLServerErrorInfo** are custom OLE DB error objects, with **ISQLServerErrorInfo** being the interface to use to obtain information of server errors, including such details as procedure name and line numbers.</span></span>  
  
```  
// Get the SQL Server custom error object.  
if(FAILED(hr=pIErrorRecords->GetCustomErrorObject(  
   nRec, IID_ISQLServerErrorInfo,  
   (IUnknown**)&pISQLServerErrorErrorInfo)))  
```  
  
 <span data-ttu-id="e4f81-108">Outro modo de obter um ponteiro **ISQLServerErrorInfo** é chamar o método **QueryInterface** em um ponteiro **ISQLErrorInfo** já obtido.</span><span class="sxs-lookup"><span data-stu-id="e4f81-108">Another way to get an **ISQLServerErrorInfo** pointer is to call the **QueryInterface** method on an already-obtained **ISQLErrorInfo** pointer.</span></span> <span data-ttu-id="e4f81-109">Observe que pelo fato de **ISQLServerErrorInfo** conter um superconjunto das informações disponíveis de **ISQLErrorInfo**, faz sentido passar diretamente para **ISQLServerErrorInfo** por meio de **GetCustomerErrorObject**.</span><span class="sxs-lookup"><span data-stu-id="e4f81-109">Note that because **ISQLServerErrorInfo** contains a superset of the information available from **ISQLErrorInfo**, it makes sense to go directly to **ISQLServerErrorInfo** through **GetCustomerErrorObject**.</span></span>  
  
 <span data-ttu-id="e4f81-110">A interface **ISQLServerErrorInfo** expõe uma função de membro, [ISQLServerErrorInfo::GetErrorInfo](../native-client-ole-db-interfaces/isqlservererrorinfo-geterrorinfo-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="e4f81-110">The **ISQLServerErrorInfo** interface exposes one member function, [ISQLServerErrorInfo::GetErrorInfo](../native-client-ole-db-interfaces/isqlservererrorinfo-geterrorinfo-ole-db.md).</span></span> <span data-ttu-id="e4f81-111">A função retorna um ponteiro para uma estrutura SSERRORINFO e um ponteiro para um buffer de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="e4f81-111">The function returns a pointer to an SSERRORINFO structure and a pointer to a string buffer.</span></span> <span data-ttu-id="e4f81-112">Ambos os ponteiros referenciam a memória que precisa ser desalocada pelo consumidor usando o método **IMalloc::Free**.</span><span class="sxs-lookup"><span data-stu-id="e4f81-112">Both pointers reference memory the consumer must deallocate by using the **IMalloc::Free** method.</span></span>  
  
 <span data-ttu-id="e4f81-113">Os membros da estrutura SSERRORINFO são interpretados pelo consumidor como a seguir.</span><span class="sxs-lookup"><span data-stu-id="e4f81-113">SSERRORINFO structure members are interpreted by the consumer as follows.</span></span>  
  
|<span data-ttu-id="e4f81-114">Membro</span><span class="sxs-lookup"><span data-stu-id="e4f81-114">Member</span></span>|<span data-ttu-id="e4f81-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="e4f81-115">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e4f81-116">*pwszMessage*</span><span class="sxs-lookup"><span data-stu-id="e4f81-116">*pwszMessage*</span></span>|<span data-ttu-id="e4f81-117">Mensagem de erro do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e4f81-117">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error message.</span></span> <span data-ttu-id="e4f81-118">Idêntico à cadeia de caracteres retornada em **IErrorInfo::GetDescription**.</span><span class="sxs-lookup"><span data-stu-id="e4f81-118">Identical to the string returned in **IErrorInfo::GetDescription**.</span></span>|  
|<span data-ttu-id="e4f81-119">*pwszServer*</span><span class="sxs-lookup"><span data-stu-id="e4f81-119">*pwszServer*</span></span>|<span data-ttu-id="e4f81-120">O nome da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para a sessão.</span><span class="sxs-lookup"><span data-stu-id="e4f81-120">Name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for the session.</span></span>|  
|<span data-ttu-id="e4f81-121">*pwszProcedure*</span><span class="sxs-lookup"><span data-stu-id="e4f81-121">*pwszProcedure*</span></span>|<span data-ttu-id="e4f81-122">Se apropriado, o nome do procedimento no qual o erro foi originado.</span><span class="sxs-lookup"><span data-stu-id="e4f81-122">If appropriate, the name of the procedure in which the error originated.</span></span> <span data-ttu-id="e4f81-123">Uma cadeia de caracteres vazia caso contrário.</span><span class="sxs-lookup"><span data-stu-id="e4f81-123">An empty string otherwise.</span></span>|  
|<span data-ttu-id="e4f81-124">*lNative*</span><span class="sxs-lookup"><span data-stu-id="e4f81-124">*lNative*</span></span>|<span data-ttu-id="e4f81-125">O número do erro nativo do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e4f81-125">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native error number.</span></span> <span data-ttu-id="e4f81-126">Idêntico ao valor retornado no parâmetro *plNativeError* de **ISQLErrorInfo::GetSQLInfo**.</span><span class="sxs-lookup"><span data-stu-id="e4f81-126">Identical to the value returned in the *plNativeError* parameter of **ISQLErrorInfo::GetSQLInfo**.</span></span>|  
|<span data-ttu-id="e4f81-127">*bState*</span><span class="sxs-lookup"><span data-stu-id="e4f81-127">*bState*</span></span>|<span data-ttu-id="e4f81-128">O estado de uma mensagem de erro do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e4f81-128">State of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error message.</span></span>|  
|<span data-ttu-id="e4f81-129">*bClass*</span><span class="sxs-lookup"><span data-stu-id="e4f81-129">*bClass*</span></span>|<span data-ttu-id="e4f81-130">A severidade de uma mensagem de erro do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e4f81-130">Severity of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error message.</span></span>|  
|<span data-ttu-id="e4f81-131">*wLineNumber*</span><span class="sxs-lookup"><span data-stu-id="e4f81-131">*wLineNumber*</span></span>|<span data-ttu-id="e4f81-132">Quando aplicável, o número da linha de um procedimento armazenado no qual o erro ocorreu.</span><span class="sxs-lookup"><span data-stu-id="e4f81-132">When applicable, the line number of a stored procedure on which the error occurred.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e4f81-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e4f81-133">See Also</span></span>  
 <span data-ttu-id="e4f81-134">[Los](errors.md) </span><span class="sxs-lookup"><span data-stu-id="e4f81-134">[Errors](errors.md) </span></span>  
 [<span data-ttu-id="e4f81-135">RAISERROR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e4f81-135">RAISERROR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/raiserror-transact-sql)  
  
  
