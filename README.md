# box-it
class Box
{
    int l;
    int b;
    int h;
    
    public:
        Box() : l(0), b(0), h(0) {}
        Box(int length, int breadth, int height) : l(length), b(breadth), h(height) {}
        Box(const Box &box) : l(box.l), b(box.b), h(box.h) {}
        
        int getLength() const { return l;}
        int getBreadth() const {return b;}
        int getHeight() const {return h;}
        
        long long CalculateVolume() const { return (long long)l*(long long)h*(long long)b;}
        
        bool operator<(const Box &b) const
        {
            return this->l < b.l || 
            (this->b < b.b && this->l == b.l) ||
            (this->h < b.h && this->b == b.b && this->l == b.l);
        }
        
        friend ostream& operator<<(ostream& out, const Box& B)
        {
            out << B.l << " " << B.b << " " << B.h;
            return out;
        }
};
