---
title: Adicionando um procedimento armazenado estendido a SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], adding
- adding extended stored procedures
- collations [SQL Server], extended stored procedures
ms.assetid: 10f1bb74-3b43-4efd-b7ab-7a85a8600a50
author: rothja
ms.author: jroth
ms.openlocfilehash: 03ac8c2a0fa9ce77db59d50b3a7b9da42415e013
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576401"
---
# <a name="adding-an-extended-stored-procedure-to-sql-server"></a><span data-ttu-id="ed19b-102">Adicionando um procedimento armazenado estendido ao SQL Server</span><span class="sxs-lookup"><span data-stu-id="ed19b-102">Adding an Extended Stored Procedure to SQL Server</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="ed19b-103">Em vez disso, use a integração CLR.</span><span class="sxs-lookup"><span data-stu-id="ed19b-103">Use CLR Integration instead.</span></span>  
  
 <span data-ttu-id="ed19b-104">Uma DLL que contém funções de procedimento armazenado estendido funciona como uma extensão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed19b-104">A DLL that contains extended stored procedure functions acts as an extension to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ed19b-105">Para instalar a DLL, copie o arquivo para um diretório, como aquele que contém os [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] arquivos dll padrão (C:\Program Files\Microsoft SQL Server\MSSQL12.0.\* x\*\MSSQL\Binn por padrão).</span><span class="sxs-lookup"><span data-stu-id="ed19b-105">To install the DLL, copy the file to a directory, such as the one that contains the standard [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] DLL files (C:\Program Files\Microsoft SQL Server\MSSQL12.0.*x*\MSSQL\Binn by default).</span></span>  
  
 <span data-ttu-id="ed19b-106">Depois que uma DLL de procedimento armazenado estendido for copiada no servidor, um administrador do sistema do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deve registrar no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] todas as funções de procedimento armazenado estendido na DLL.</span><span class="sxs-lookup"><span data-stu-id="ed19b-106">After the extended stored procedure DLL has been copied to the server, a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator must register to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] each extended stored procedure function in the DLL.</span></span> <span data-ttu-id="ed19b-107">Isso é feito por meio do uso do procedimento armazenado de sistema sp_addextendedproc.</span><span class="sxs-lookup"><span data-stu-id="ed19b-107">This is done using the sp_addextendedproc system stored procedure.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ed19b-108">O administrador do sistema deve examinar inteiramente um procedimento armazenado estendido para garantir que ele não contenha código perigoso ou mal-intencionado, antes de adicioná-lo ao servidor e conceder permissões de execução a outros usuários.</span><span class="sxs-lookup"><span data-stu-id="ed19b-108">The system administrator should thoroughly review an extended stored procedure to ensure that it does not contain harmful or malicious code before adding it to the server and granting execute permissions to other users.</span></span>  <span data-ttu-id="ed19b-109">Valide todas as entradas de usuário.</span><span class="sxs-lookup"><span data-stu-id="ed19b-109">Validate all user input.</span></span> <span data-ttu-id="ed19b-110">Não concatene uma entrada de usuário antes de validá-la.</span><span class="sxs-lookup"><span data-stu-id="ed19b-110">Do not concatenate user input before validating it.</span></span> <span data-ttu-id="ed19b-111">Nunca execute um comando construído por uma entrada de usuário inválida.</span><span class="sxs-lookup"><span data-stu-id="ed19b-111">Never execute a command constructed from unvalidated user input.</span></span>  
  
 <span data-ttu-id="ed19b-112">O primeiro parâmetro de sp_addextendedproc especifica o nome da função e o segundo, o nome da DLL em que reside essa função.</span><span class="sxs-lookup"><span data-stu-id="ed19b-112">The first parameter of sp_addextendedproc specifies the name of the function, and the second parameter specifies the name of the DLL in which that function resides.</span></span> <span data-ttu-id="ed19b-113">É recomendável especificar o caminho completo da DLL.</span><span class="sxs-lookup"><span data-stu-id="ed19b-113">It is recommended that you specify the complete path of the DLL.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ed19b-114">As DLLs existentes que não foram registradas com um caminho completo não funcionarão depois da atualização para o SQL Server 2005 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="ed19b-114">Existing DLLs that were not registered with a complete path will not work after upgrading to SQL Server 2005 or later.</span></span> <span data-ttu-id="ed19b-115">Para corrigir o problema, use sp_dropextendedproc para cancelar o registro da DLL e registrá-la novamente com sp_addextendedproc, especificando o caminho completo.</span><span class="sxs-lookup"><span data-stu-id="ed19b-115">To correct the problem, use sp_dropextendedproc to unregister the DLL, and then reregister it with sp_addextendedproc, specifying the complete path.</span></span>  
  
 <span data-ttu-id="ed19b-116">O nome da função especificada em `sp_addextendedproc` deve ser exatamente igual, inclusive maiúsculas e minúsculas, ao nome da função na DLL.</span><span class="sxs-lookup"><span data-stu-id="ed19b-116">The name of the function specified in `sp_addextendedproc` must be exactly the same, including the case, as the function's name in the DLL.</span></span> <span data-ttu-id="ed19b-117">Por exemplo, esse comando registra uma função `xp_hello,`, localizada em uma dll denominada `xp_hello.dll`, como um procedimento armazenado do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="ed19b-117">For example, this command registers a function `xp_hello,` located in a dll named `xp_hello.dll`, as a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] extended stored procedure:</span></span>  
  
```  
sp_addextendedproc 'xp_hello', 'c:\Program Files\Microsoft SQL Server\MSSQL12.0.MSSQLSERVER\MSSQL\Binn\xp_hello.dll';  
```  
  
 <span data-ttu-id="ed19b-118">Se o nome da função especificado em `sp_addextendedproc` não corresponder exatamente ao nome da função na DLL, o novo nome será registrado no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], mas o nome não poderá ser usado.</span><span class="sxs-lookup"><span data-stu-id="ed19b-118">If the name of the function specified in `sp_addextendedproc` does not exactly match the function name in the DLL, the new name will be registered in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], but the name will not be usable.</span></span> <span data-ttu-id="ed19b-119">Por exemplo, embora o `xp_Hello` esteja registrado como um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] procedimento armazenado estendido localizado em `xp_hello.dll` , [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o não será capaz de localizar a função na dll se você usar `xp_Hello` para chamar a função posteriormente.</span><span class="sxs-lookup"><span data-stu-id="ed19b-119">For example, although `xp_Hello` is registered as a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] extended stored procedure located in `xp_hello.dll`, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will not be able to find the function in the DLL if you use `xp_Hello` to call the function later.</span></span>  
  
```  
--Register the function (xp_hello) with an initial upper case  
sp_addextendedproc 'xp_Hello', 'c:\xp_hello.dll';  
  
--Use the newly registered name to call the function  
DECLARE @txt varchar(33);  
EXEC xp_Hello @txt OUTPUT;  
  
--This is the error message  
Server: Msg 17750, Level 16, State 1, Procedure xp_Hello, Line 1  
Could not load the DLL xp_hello.dll, or one of the DLLs it references. Reason: 127(The specified procedure could not be found.).  
```  
  
 <span data-ttu-id="ed19b-120">Se o nome da função especificado em `sp_addextendedproc` corresponder exatamente ao nome da função na DLL, e a ordenação da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] diferenciar maiúsculas e minúsculas, o usuário poderá chamar o procedimento armazenado estendido usando qualquer combinação de letras maiúsculas e minúsculas no nome.</span><span class="sxs-lookup"><span data-stu-id="ed19b-120">If the name of the function specified in `sp_addextendedproc` matches exactly the function name in the DLL, and the collation of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance is case-insensitive, the user can call the extended stored procedure using any combination of lower- and upper-case letters of the name.</span></span>  
  
```  
--Register the function (xp_hello)  
sp_addextendedproc 'xp_hello', 'c:\xp_hello.dll';  
  
--The following will succeed in calling xp_hello  
DECLARE @txt varchar(33);  
EXEC xp_Hello @txt OUTPUT;  
  
DECLARE @txt varchar(33);  
EXEC xp_HelLO @txt OUTPUT;  
  
DECLARE @txt varchar(33);  
EXEC xp_HELLO @txt OUTPUT;  
```  
  
 <span data-ttu-id="ed19b-121">Quando a ordenação da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] diferenciar maiúsculas de minúsculas, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não poderá chamar o procedimento armazenado estendido – mesmo que tenha sido registrado exatamente com o mesmo nome e ordenação da função na DLL –, se o procedimento for chamado com um uso de maiúsculas e minúsculas diferente.</span><span class="sxs-lookup"><span data-stu-id="ed19b-121">When the collation of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance is case-sensitive, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will not be able to call the extended stored procedure -- even if it was registered with exactly the same name and collation as the function in the DLL -- if the procedure is called with a different case.</span></span>  
  
```  
--Register the function (xp_hello)  
sp_addextendedproc 'xp_hello', 'c:\xp_hello.dll';  
  
--The following will result in an error  
DECLARE @txt varchar(33);  
EXEC xp_HELLO @txt OUTPUT;  
  
--This is the error  
Server: Msg 2812, Level 16, State 62, Line 1  
```  
  
 <span data-ttu-id="ed19b-122">Não é necessário parar e reiniciar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed19b-122">It is not necessary to stop and restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed19b-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ed19b-123">See Also</span></span>  
 <span data-ttu-id="ed19b-124">[&#41;&#40;Transact-SQL de sp_addextendedproc](/sql/relational-databases/system-stored-procedures/sp-addextendedproc-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed19b-124">[sp_addextendedproc &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addextendedproc-transact-sql) </span></span>  
 [<span data-ttu-id="ed19b-125">sp_dropextendedproc &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ed19b-125">sp_dropextendedproc &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-dropextendedproc-transact-sql)  
  
  
