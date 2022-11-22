class Node {
    constructor(element, next) {
        this.element = element
        this.next = next
    }
}

const node = new Node(10)

function defaultEqualsFn(a, b) {
    return a === b
}

class LinkedList {
    constructor(equalsFn = defaultEqualsFn) {
        this.head = undefined
        this.count = 0
        this.equalsFn = equalsFn
    }
    
    push(element) {
        const node = new Node(element)
        if (this.isEmpty()) {
            this.head = node
        } else {
            let current = this.head
            while(current.next !== undefined) {
                current = current.next
            }
            
            current.next = node
            
        }
        this.count++
    }
    
    insert(element, position) {
        if (position >= 0 && position <= this.count) {
            const node = new Node(element)
            
            if (position === 0) {
                node.next = this.head
                this.head = node
                this.count++
                return true
            }
            
            const previous = this.getElementAt(position - 1)
            const current = previous.next
            
            node.next = current
            previous.next = node
            this.count++
            return true
        }
        return false
        
    }
    
    remove() {
        return this.removeAt(this.count - 1)
    }
    
    removeAt(position) {
        if (position >= 0 && position < this.count) {
            if (position === 0) {
                this.head = this.head.next
                
            } else {
                const previous = this.getElementAt(position - 1)
                const current = previous.next
                previous.next = current.next
            }
            this.count--
            return true
        }
        return false
    }
    
    getElementAt(position) {
        if (position >= 0 && position < this.count) {
            if (position === 0) {
                return this.head
            }
            let current = this.head.next
            for (let i = 1; i < position ;i++) {
                current = current.next
            }
            return current
        }
        return undefined
    }
    
    indexOf(element) {
        if (!this.isEmpty()) {
            if (this.equalsFn(this.head.element, element)) {
                return 0
            }
            let current = this.head.next
            for (let i = 1; i < this.count;i++) {
                if (this.equalsFn(current.element, element)) {
                    return i
                }
                if (current.next) {
                    current = current.next
                }
            }
        } 
        return undefined
    }
    
    size() {
        return this.count
    }
    
    isEmpty() {
        return this.size() === 0
    }
    
    toString() {
        if (this.isEmpty()) {
            return ''
        }
        
        let current = this.head
        let objString = `${current.element}`
        
        for (let i = 1; i < this.count;i++) {
            objString += `, ${current.next.element}`
            if (current.next) {
                current = current.next
            }
        }
        
        return objString
    }
}

const linkedList = new LinkedList()

console.log(linkedList.isEmpty(), linkedList.size())
console.log(linkedList.toString())

linkedList.push(10)
console.log(linkedList.toString(), 'a1')
linkedList.push(20)
console.log(linkedList.toString(), 'b1')
linkedList.push(30)
console.log(linkedList.toString(), 'c1')

console.log(linkedList.indexOf(20))

console.log(linkedList.getElementAt(3))

linkedList.insert(40, 3)
linkedList.insert(11, 0)
console.log(linkedList.getElementAt(0))
linkedList.insert(41, 3)
console.log(linkedList.getElementAt(3))
console.log(linkedList.isEmpty(), linkedList.size())

console.log(linkedList.head.next)

console.log(linkedList.toString())
console.log('= = = = = = = =')
linkedList.remove()
console.log(linkedList.toString())
linkedList.removeAt(0)
console.log(linkedList.toString())
linkedList.removeAt(2)
console.log(linkedList.toString())
linkedList.remove()
console.log(linkedList.toString())
