匹配所有Number直接量的正则


var numreg = /^-?[0-9]\d*$|(0x)?[0-9a-fA-F]+|0?[0-7]*|^-?([1-9]\d*\.\d*|0\.\d*[1-9]\d*|0?\.0+|0)$/g；



function UTF8code(str) {
            const code = encodeURIComponent(str);
            const bytes = [];

            for (let i = 0; i < code.length; i++) {
                const c = code.charAt(i)
                    if (c === '%') {
                        const hex = code.charAt(i + 1) + code.charAt(i + 2)
                        const hexVal = parseInt(hex, 16)
                        bytes.push(hexVal)
                        i += 2
                    } else {
                bytes.push(c.charCodeAt(0))
                }
            }
        return bytes;
        }


写一个正则表达式，匹配所有的字符串直接量，单引号和双引号

var numreg2 = /[\u0021-\u007E]{6,16}|[\x21-\x7E]{6,16}|(['"])(?:(?!\1).)*?\1/；
