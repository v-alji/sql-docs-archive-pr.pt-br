---
title: srv_convert (API de Procedimento Armazenado Estendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_convert
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_convert
ms.assetid: 216b4a31-786e-4361-8a33-e5f6e9790f90
author: rothja
ms.author: jroth
ms.openlocfilehash: 30a0ea356f017ed3d1b3ecc85cf483b4553e120a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583058"
---
# <a name="srv_convert-extended-stored-procedure-api"></a><span data-ttu-id="29366-102">srv_convert (API de procedimento armazenado estendido)</span><span class="sxs-lookup"><span data-stu-id="29366-102">srv_convert (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="29366-103">Em vez disso, use a Integração CLR.</span><span class="sxs-lookup"><span data-stu-id="29366-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="29366-104">Altera dados de um tipo de dados para outro.</span><span class="sxs-lookup"><span data-stu-id="29366-104">Changes data from one data type to another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29366-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="29366-105">Syntax</span></span>  
  
```  
  
int srv_convert (  
SRV_PROC *  
srvproc  
,  
int  
srctype  
,  
void *  
src  
,  
DBINT  
srclen  
,  
int  
desttype  
,  
void *  
dest  
,  
DBINT  
destlen  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="29366-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="29366-106">Arguments</span></span>  
 <span data-ttu-id="29366-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="29366-107">*srvproc*</span></span>  
 <span data-ttu-id="29366-108">É um ponteiro para a estrutura SRV_PROC que atua como identificador de uma conexão de cliente específica.</span><span class="sxs-lookup"><span data-stu-id="29366-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="29366-109">A estrutura contém todas as informações de controle que a biblioteca de APIs de procedimento armazenado estendido usa para gerenciar as comunicações e os dados entre o aplicativo e o cliente.</span><span class="sxs-lookup"><span data-stu-id="29366-109">The structure contains all the control information that the Extended Stored Procedure API uses to manage communications and data between the application and the client.</span></span> <span data-ttu-id="29366-110">Caso o identificador *srvproc* seja fornecido, ele será passado para a função de manipulador de erro da API de Procedimento Armazenado Estendido quando ocorrer um erro.</span><span class="sxs-lookup"><span data-stu-id="29366-110">If the *srvproc* handle is supplied, it is passed to the Extended Stored Procedure API error handler function when an error occurs.</span></span>  
  
 <span data-ttu-id="29366-111">*srctype*</span><span class="sxs-lookup"><span data-stu-id="29366-111">*srctype*</span></span>  
 <span data-ttu-id="29366-112">Especifica o tipo de dados dos dados a serem convertidos.</span><span class="sxs-lookup"><span data-stu-id="29366-112">Specifies the data type of the data to be converted.</span></span> <span data-ttu-id="29366-113">Este parâmetro pode ser qualquer um dos tipos de dados da API de procedimento armazenado estendido.</span><span class="sxs-lookup"><span data-stu-id="29366-113">This parameter can be any of the Extended Store Procedure API data types.</span></span>  
  
 <span data-ttu-id="29366-114">*src*</span><span class="sxs-lookup"><span data-stu-id="29366-114">*src*</span></span>  
 <span data-ttu-id="29366-115">Trata-se de um ponteiro para os dados a serem convertidos.</span><span class="sxs-lookup"><span data-stu-id="29366-115">Is a pointer to the data to be converted.</span></span> <span data-ttu-id="29366-116">Este parâmetro pode ser qualquer um dos tipos de dados da API de procedimento armazenado estendido.</span><span class="sxs-lookup"><span data-stu-id="29366-116">This parameter can be any of the Extended Store Procedure API data types.</span></span>  
  
 <span data-ttu-id="29366-117">*srclen*</span><span class="sxs-lookup"><span data-stu-id="29366-117">*srclen*</span></span>  
 <span data-ttu-id="29366-118">Especifica o comprimento, em bytes, dos dados a serem convertidos.</span><span class="sxs-lookup"><span data-stu-id="29366-118">Specifies the length, in bytes, of the data to be converted.</span></span> <span data-ttu-id="29366-119">Caso *srclen* seja 0, **srv_convert** colocará um valor nulo na variável de destino.</span><span class="sxs-lookup"><span data-stu-id="29366-119">If *srclen* is 0, **srv_convert** places a null value in the destination variable.</span></span> <span data-ttu-id="29366-120">A menos que seja 0, esse parâmetro é ignorado para tipos de dados com comprimento fixo, quando se pressupõe que os dados sejam NULL.</span><span class="sxs-lookup"><span data-stu-id="29366-120">Unless it is 0, this parameter is ignored for fixed-length data types, in which case the source data is assumed to be NULL.</span></span> <span data-ttu-id="29366-121">Para dados do tipo de dados SRVCHAR, um comprimento igual a -1 indica a cadeia de caracteres é terminada em nulo.</span><span class="sxs-lookup"><span data-stu-id="29366-121">For data of the SRVCHAR data type, a length of -1 indicates the string is null-terminated.</span></span>  
  
 <span data-ttu-id="29366-122">*desttype*</span><span class="sxs-lookup"><span data-stu-id="29366-122">*desttype*</span></span>  
 <span data-ttu-id="29366-123">Especifica o tipo de dados no qual converter a origem.</span><span class="sxs-lookup"><span data-stu-id="29366-123">Specifies the data type to convert the source to.</span></span> <span data-ttu-id="29366-124">Este parâmetro pode ser qualquer um dos tipos de dados da API de procedimento armazenado estendido.</span><span class="sxs-lookup"><span data-stu-id="29366-124">This parameter can be any of the Extended Store Procedure API data types.</span></span>  
  
 <span data-ttu-id="29366-125">*dest*</span><span class="sxs-lookup"><span data-stu-id="29366-125">*dest*</span></span>  
 <span data-ttu-id="29366-126">Trata-se de um ponteiro para a variável de destino que recebe dados convertidos.</span><span class="sxs-lookup"><span data-stu-id="29366-126">Is a pointer to the destination variable that receives converted data.</span></span> <span data-ttu-id="29366-127">Caso esse ponteiro seja NULL, **srv_convert** chamará o manipulador de erro fornecido pelo usuário, se houver, e retornará -1.</span><span class="sxs-lookup"><span data-stu-id="29366-127">If this pointer is NULL, **srv_convert** calls the user-supplied error handler ,if any, and returns -1.</span></span>  
  
 <span data-ttu-id="29366-128">Caso *desttype* seja SRVDECIMAL ou SRVNUMERIC, o parâmetro *dest* deverá ser um ponteiro para uma estrutura DBNUMERIC ou DBDECIMAL com os campos de precisão e escala da estrutura já definidos com os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="29366-128">If *desttype* is SRVDECIMAL or SRVNUMERIC, the *dest* parameter must be a pointer to a DBNUMERIC or DBDECIMAL structure with the precision and scale fields of the structure already set to the desired values.</span></span> <span data-ttu-id="29366-129">É possível usar DEFAULTPRECISION para especificar uma precisão padrão, e DEFAULTSCALE para especificar uma escala padrão.</span><span class="sxs-lookup"><span data-stu-id="29366-129">You can use DEFAULTPRECISION to specify a default precision, and DEFAULTSCALE to specify a default scale.</span></span>  
  
 <span data-ttu-id="29366-130">*destlen*</span><span class="sxs-lookup"><span data-stu-id="29366-130">*destlen*</span></span>  
 <span data-ttu-id="29366-131">Especifica o comprimento, em bytes, da variável de destino.</span><span class="sxs-lookup"><span data-stu-id="29366-131">Specifies the length, in bytes, of the destination variable.</span></span> <span data-ttu-id="29366-132">Esse parâmetro é ignorado para tipos de dados com comprimento fixo.</span><span class="sxs-lookup"><span data-stu-id="29366-132">This parameter is ignored for fixed-length data types.</span></span> <span data-ttu-id="29366-133">Para uma variável de destino do tipo SRVCHAR, o valor igual a *destlen* deve ser o tamanho total do espaço do buffer de destino.</span><span class="sxs-lookup"><span data-stu-id="29366-133">For a destination variable of type SRVCHAR, the value of *destlen* must be the total length of the destination buffer space.</span></span> <span data-ttu-id="29366-134">Um comprimento igual a -1 para uma variável de destino do tipo SRVCHAR ou SRVBINARY indica se há espaço suficiente disponível.</span><span class="sxs-lookup"><span data-stu-id="29366-134">A length of -1 for a destination variable of type SRVCHAR or SRVBINARY indicates there is sufficient space available.</span></span> <span data-ttu-id="29366-135">Para uma variável de destino do tipo *srvchar*, um tamanho igual a -1 faz com que a cadeia de caracteres termine em nulo.</span><span class="sxs-lookup"><span data-stu-id="29366-135">For a destination variable of type *srvchar*, a length of -1 causes the character string to be null-terminated.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="29366-136">Retornos</span><span class="sxs-lookup"><span data-stu-id="29366-136">Returns</span></span>  
 <span data-ttu-id="29366-137">O comprimento dos dados convertidos, em bytes, caso a conversão do tipo de dados tenha êxito.</span><span class="sxs-lookup"><span data-stu-id="29366-137">The length of the converted data, in bytes, if the data type conversion succeeds.</span></span> <span data-ttu-id="29366-138">Quando **srv_convert** encontra uma solicitação para uma conversão para a qual não dá suporte, ele chama o manipulador de erro fornecido pelo desenvolvedor, se houver, define um número de erro global e retorna -1.</span><span class="sxs-lookup"><span data-stu-id="29366-138">When **srv_convert** encounters a request for a conversion it does not support, it calls the developer-supplied error handler, if any, sets a global error number, and returns -1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29366-139">Comentários</span><span class="sxs-lookup"><span data-stu-id="29366-139">Remarks</span></span>  
 <span data-ttu-id="29366-140">A função **srv_willconvert** determina se uma conversão específica é permitida.</span><span class="sxs-lookup"><span data-stu-id="29366-140">The **srv_willconvert** function determines whether a particular conversion is allowed.</span></span>  
  
 <span data-ttu-id="29366-141">A conversão para os tipos de dados numéricos aproximados SRVFLT4 ou SRVFLT8 pode resultar em uma certa perda de precisão.</span><span class="sxs-lookup"><span data-stu-id="29366-141">Converting to the approximate numeric data types SRVFLT4 or SRVFLT8 can result in some loss of precision.</span></span> <span data-ttu-id="29366-142">A conversão dos tipos de dados numéricos aproximados SRVFLT4 ou SRVFLT8 em SRVCHAR ou SRVTEXT também pode resultar em alguma perda de precisão.</span><span class="sxs-lookup"><span data-stu-id="29366-142">Converting from the approximate numeric data types SRVFLT4 or SRVFLT8 to SRVCHAR or SRVTEXT can also result in some loss of precision.</span></span>  
  
 <span data-ttu-id="29366-143">A conversão em SRVFLT*x*, SRVINT*x*, SRVMONEY, SRVMONEY4, SRVDECIMAL ou SRVNUMERIC pode resultar em estouro, caso o número seja maior que o valor máximo do destino ou em estouro negativo, caso o número seja menor que o valor mínimo do destino.</span><span class="sxs-lookup"><span data-stu-id="29366-143">Converting to SRVFLT*x*, SRVINT*x*, SRVMONEY, SRVMONEY4, SRVDECIMAL, or SRVNUMERIC can result in overflow if the number is larger than the maximum value of the destination, or in underflow if the number is smaller than the minimum value of the destination.</span></span> <span data-ttu-id="29366-144">Caso o estouro ocorra durante a conversão em SRVCHAR ou SRVTEXT, o primeiro caractere do valor resultante contém um asterisco (\*) para indicar o erro.</span><span class="sxs-lookup"><span data-stu-id="29366-144">If overflow occurs when converting to SRVCHAR or SRVTEXT, the first character of the resulting value contains an asterisk (\*) to indicate the error.</span></span>  
  
 <span data-ttu-id="29366-145">Ao converter SRVCHAR em SRVBINARY, **srv_convert** interpreta SRVCHAR como hexadecimal, independentemente da cadeia de caracteres conter um 0 à esquerda.</span><span class="sxs-lookup"><span data-stu-id="29366-145">When converting SRVCHAR to SRVBINARY, **srv_convert** interprets SRVCHAR as hexadecimal, whether or not the string contains a leading 0.</span></span> <span data-ttu-id="29366-146">Ao converter SRVBINARY em SRVCHAR, **srv_convert** cria uma cadeia de caracteres hexadecimal sem um 0 à esquerda.</span><span class="sxs-lookup"><span data-stu-id="29366-146">When converting SRVBINARY to SRVCHAR, **srv_convert** creates a hexadecimal string without a leading 0.</span></span> <span data-ttu-id="29366-147">Em todos os demais casos, uma conversão para ou do tipo de dados SRVBINARY é uma cópia de bit direta.</span><span class="sxs-lookup"><span data-stu-id="29366-147">In all other cases, a conversion to or from the SRVBINARY data type is a straight bit-copy.</span></span>  
  
 <span data-ttu-id="29366-148">Em determinados casos, isso pode ser útil na conversão de um tipo de dados em si mesmo.</span><span class="sxs-lookup"><span data-stu-id="29366-148">In certain cases, it can be useful to convert a data type to itself.</span></span> <span data-ttu-id="29366-149">Por exemplo, a conversão de SRVCHAR em SRVCHAR com *destlen* igual -1 adiciona um terminador nulo a uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="29366-149">For example, converting SRVCHAR to SRVCHAR with a *destlen* of -1 adds a null terminator to a string.</span></span>  
  
 <span data-ttu-id="29366-150">Para obter uma descrição dos tipos de dados e das conversões de tipo de dados da API de Procedimento Armazenado Estendido, consulte [Tipos de dados &#40;API de Procedimento Armazenado Estendido&#41;](data-types-extended-stored-procedure-api.md).</span><span class="sxs-lookup"><span data-stu-id="29366-150">For a description of data types and Extended Store Procedure API data type conversions, see [Data Types &#40;Extended Stored Procedure API&#41;](data-types-extended-stored-procedure-api.md).</span></span>  
  
 <span data-ttu-id="29366-151">A função **srv_convert** pode falhar por várias razões:</span><span class="sxs-lookup"><span data-stu-id="29366-151">The **srv_convert** function can fail for several reasons:</span></span>  
  
-   <span data-ttu-id="29366-152">A conversão solicitada não está disponível.</span><span class="sxs-lookup"><span data-stu-id="29366-152">The requested conversion is not available.</span></span>  
  
-   <span data-ttu-id="29366-153">A conversão resultou em truncamento, estouro ou perda de precisão na variável de destino.</span><span class="sxs-lookup"><span data-stu-id="29366-153">The conversion resulted in truncation, overflow, or loss of precision in the destination variable.</span></span>  
  
-   <span data-ttu-id="29366-154">Ocorreu um erro de sintaxe durante a conversão de uma cadeia de caracteres em um tipo de dados numérico.</span><span class="sxs-lookup"><span data-stu-id="29366-154">A syntax error occurred while converting a character string to a numeric data type.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="29366-155">Você deve examinar totalmente o código-fonte de procedimentos armazenados estendidos e deve testar as DLLs compiladas antes de instalá-las em um servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="29366-155">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="29366-156">Para obter informações sobre revisão e testes de segurança, consulte este [site da Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="29366-156">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29366-157">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="29366-157">See Also</span></span>  
 <span data-ttu-id="29366-158">[srv_setutype &#40;API de procedimento armazenado estendido&#41;](srv-setutype-extended-stored-procedure-api.md) </span><span class="sxs-lookup"><span data-stu-id="29366-158">[srv_setutype &#40;Extended Stored Procedure API&#41;](srv-setutype-extended-stored-procedure-api.md) </span></span>  
 [<span data-ttu-id="29366-159">srv_willconvert &#40;API de Procedimento Armazenado Estendido&#41;</span><span class="sxs-lookup"><span data-stu-id="29366-159">srv_willconvert &#40;Extended Stored Procedure API&#41;</span></span>](srv-willconvert-extended-stored-procedure-api.md)  
  
  
