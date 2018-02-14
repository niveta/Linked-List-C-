//
//  lab3.h
//  lab3
//
//  Created by Niveta Chowdhry on 2/7/18.
//  Copyright © 2018 Niveta Chowdhry. All rights reserved.
//
#include <iostream>

template <typename T>
class DList{
    struct Node{
        T data_;
        Node* next_;
        Node* prev_;
        Node(const T& data=T{},Node* next=nullptr, Node* prev=nullptr){
            data_=data;
            next_=next;
            prev_=prev;
        }
    };
    Node* front_;
    Node* back_;
public:
    DList(){
        front_=nullptr;
        back_=nullptr;
    }
    void push_front(const T& data);
    void push_back(const T& data);
    void pop_front();
    void pop_back();
    void print() const;
    void reversePrint() const;
    ~DList();
};


template <typename T>
void DList<T>::push_front(const T& data){
    //make a new node with data ,next pointer gets same as front prev is nullptr
    Node* nn=new Node(data,front_,nullptr);
    if(front_!=nullptr){
        //make front's prev point to new node
        front_->prev_ = nn;
    }
    else{
        
        back_=nn;
    }
    //make front point to new node
    front_=nn;
}

template <typename T>
void DList<T>::push_back(const T& data){
    Node* newN = new Node(data, nullptr, back_);
    if( back_ != nullptr){
        back_->next_ = newN;
    }
    else{
        front_ = newN;
    }
    back_ = newN;
}

template <typename T>
void DList<T>::pop_front(){
    if(front_ != nullptr){
        Node* rm = front_;
        if(front_!=back_){  //make sure we have more than one node
            front_=front_->next_; //front_=rm->next_;
            front_->prev_=nullptr;
        }
        else{
            front_=back_=nullptr;
        }
        delete rm;
    }
    
}
template <typename T>
void DList<T>::pop_back(){
    if(back_ != nullptr){
        Node* temp = back_;
        if(front_!=back_){
        back_->prev_->next_ = nullptr;
        back_ = back_->prev_;
            //std::cout << "new back data: "  << back_->data_;
        }
        else{
            front_ = back_ = nullptr;
        }
        delete temp;
    }
}
    
template <typename T>
void DList<T>::print() const{
    Node* curr=front_;
    while(curr!=nullptr){
        std::cout << curr->data_ << " ";
        curr=curr->next_;
    }
    std::cout << std::endl;
}
template <typename T>
void DList<T>::reversePrint() const{
    Node* curr=back_;
    while(curr!=nullptr){
        std::cout << curr->data_ << " ";
        curr=curr->prev_;
    }
    std::cout << std::endl;
}
template <typename T>
DList<T>::~DList(){
    Node* curr=front_;
    while(curr){
        Node* rm=curr;
        curr=curr->next_;
        delete rm;
    }
}





//Sentinel

template <typename T>
class Sentinel{
    struct Node{
        T data_;
        Node* next_;
        Node* prev_;
        Node(const T& data=T{},Node* next=nullptr, Node* prev=nullptr){
            data_=data;
            next_=next;
            prev_=prev;
        }
    };
    Node* front_;
    Node* back_;
public:
    Sentinel(){
        front_=new Node();
        back_=new Node();
        front_->next_=back_;
        back_->prev_=front_;
    }
    void push_front(const T& data);
    void push_back(const T& data);
    void pop_front();
    void pop_back();
    void print() const;
    void reversePrint() const;
    ~Sentinel();
};


template <typename T>
void Sentinel<T>::push_front(const T& data){
    Node* first=front_;
    Node* second=first->next_;
    //make a new node with data ,next pointer points to second
    //node, previous is sentinel
    Node* nn=new Node(data,second,first);
    first->next_=nn;
    second->prev_=nn;
}
template <typename T>
void Sentinel<T>::push_back(const T& data){
    Node* secondLast = back_->prev_;
    Node* nn = new Node(data, back_, secondLast);
    secondLast->next_ = nn;
    back_->prev_ = nn;    
}

template <typename T>
void Sentinel<T>::pop_front(){
    if(front_->next_ != back_){
        Node* rm = front_->next_;
        Node* rmNext = rm->next_;
        front_->next_ = rmNext;
        rmNext->prev_ = front_;
        delete rm;
    }
}

template <typename T>
void Sentinel<T>::pop_back(){
    if(back_->prev_ != front_){
        Node* rm = back_->prev_;
        Node* rmPrev = rm->prev_;
        back_->prev_ = rmPrev;
        rmPrev->next_ = back_;
        delete rm;
    }
}

template <typename T>
void Sentinel<T>::print() const{
    Node* curr=front_->next_;
    while(curr!=back_){
        std::cout << curr->data_ << " ";
        curr=curr->next_;
    }
    std::cout << std::endl;
}
template <typename T>
void Sentinel<T>::reversePrint() const{
    Node* curr=back_->prev_;
    while(curr!=front_){
        std::cout << curr->data_ << " ";
        curr=curr->prev_;
    }
    std::cout << std::endl;
}
template <typename T>
Sentinel<T>::~Sentinel(){
    Node* curr=front_;
    while(curr){
        Node* rm=curr;
        curr=curr->next_;
        delete rm;
    }
}

